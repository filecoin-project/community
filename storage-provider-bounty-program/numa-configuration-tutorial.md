# NUMA Configuration Tutorial for Filecoin Storage Providers

> A comprehensive guide to understanding, configuring, and optimizing NUMA for Filecoin storage providers.
> Last updated: June 2026

---

## Table of Contents

1. [What is NUMA?](#what-is-numa)
2. [Why NUMA Matters for Filecoin](#why-numa-matters-for-filecoin)
3. [Hardware Configuration](#hardware-configuration)
4. [Checking Your NUMA Topology](#checking-your-numa-topology)
5. [BIOS Configuration](#bios-configuration)
6. [Linux NUMA Configuration](#linux-numa-configuration)
7. [Lotus-Specific NUMA Optimization](#lotus-specific-numa-optimization)
8. [GPU and NUMA Affinity](#gpu-and-numa-affinity)
9. [Verifying NUMA Configuration](#verifying-numa-configuration)
10. [Common Pitfalls & Troubleshooting](#common-pitfalls--troubleshooting)
11. [Reference Cards](#reference-cards)

---

## What is NUMA?

**NUMA** (Non-Uniform Memory Access) is a computer memory design used in multi-socket systems where memory access time depends on the memory location relative to the processor.

### Key Concepts

| Concept | Description |
|---------|-------------|
| **NUMA Node** | A group of CPUs and their local memory. Each socket in a multi-socket system is typically one NUMA node. |
| **Local Access** | A CPU accessing memory on its own NUMA node (fast, low latency) |
| **Remote Access** | A CPU accessing memory on another NUMA node (slower, higher latency) |
| **Memory Interleaving** | Memory spread across all NUMA nodes (balanced but can cause remote access) |
| **NUMA Binding/Pinning** | Forcing a process to run on specific CPUs and use specific memory nodes |

### Why Does It Matter?

```
┌─────────────────────┐        ┌─────────────────────┐
│    NUMA Node 0       │        │    NUMA Node 1       │
│  ┌──────┐ ┌──────┐  │        │  ┌──────┐ ┌──────┐  │
│  │ CPU  │ │ CPU  │  │        │  │ CPU  │ │ CPU  │  │
│  │ 0-15 │ │ 16-31│  │        │  │ 32-47│ │ 48-63│  │
│  └──────┘ └──────┘  │        │  └──────┘ └──────┘  │
│       │              │        │       │              │
│  ┌────┴─────┐       │        │  ┌────┴─────┐       │
│  │ Memory   │       │        │  │ Memory   │       │
│  │ 128 GB   │       │        │  │ 128 GB   │       │
│  └──────────┘       │        │  └──────────┘       │
└─────────┬───────────┘        └─────────┬───────────┘
          │                              │
          └──────────┬───────────────────┘
                     │
            ┌────────┴────────┐
            │  Interconnect   │
            │  (Infinity Fabric / UPI) │
            └─────────────────┘
```

**Local memory access**: ~80-120ns latency
**Remote memory access**: ~140-200ns latency (40-70% slower)

For **Filecoin sealing**, which is memory-intensive and CPU-bound, incorrect NUMA configuration can reduce performance by 20-40%.

---

## Why NUMA Matters for Filecoin

Filecoin storage providers run several memory-intensive processes:

### Sealing Pipeline (Most Critical)

The sealing process (PoRep - Proof of Replication) is extremely NUMA-sensitive:

| Stage | Memory Usage | CPU Sensitivity | NUMA Impact |
|-------|:-----------:|:---------------:|:-----------:|
| **SDR (Stacked DRG)** | 64-128 GB | Very High | **High** — Large memory working set, benefits from local access |
| **Layer Replication** | 32-64 GB | High | **High** — Constant memory reads/writes |
| **Column Hash** | 16-32 GB | Medium | Medium |
| **Snark Proof Generation** | 8-16 GB | Low (GPU-bound) | Low |

**NUMA effects on sealing:**
- Remote memory access increases sealing time by 15-30%
- Improper CPU pinning causes cache thrashing across sockets
- Memory bandwidth saturation on one node slows all processes

### WindowPoST

WindowPoST proofs also benefit from NUMA awareness:
- Each proof loads sectors from disk into memory
- GPU must be on the same NUMA node as the CPU driving it
- Cross-node GPU communication adds latency (risk of missing deadlines)

---

## Hardware Configuration

### Target Hardware: Dual-Socket Systems

NUMA optimization matters most for systems with 2+ CPU sockets. Here are the common configurations:

#### Recommended: AMD EPYC (2-Socket)

| Component | Configuration |
|-----------|---------------|
| **CPU** | 2× AMD EPYC 9554 (64-core, 128-thread each) |
| **NUMA Nodes** | 2 nodes (128 CPUs, 256 threads total) |
| **Memory** | 512 GB DDR5-4800 (256 GB per node, 12× 32GB DIMMs per socket) |
| **GPU** | 2× NVIDIA RTX 4090 (one per NUMA node for optimal performance) |
| **Storage** | NVMe RAID 0 on each node |

#### Recommended: Intel Xeon (2-Socket)

| Component | Configuration |
|-----------|---------------|
| **CPU** | 2× Intel Xeon Platinum 8480+ (56-core, 112-thread each) |
| **NUMA Nodes** | 2-4 nodes (sub-NUMA clustering may split each socket) |
| **Memory** | 512 GB DDR5-4800 (256 GB per socket, 8× 32GB DIMMs per socket) |
| **GPU** | 2× NVIDIA RTX 4090 (one per socket) |
| **Storage** | NVMe RAID 0 on each node |

#### Entry Level: Single Socket

| Component | Configuration |
|-----------|---------------|
| **CPU** | 1× AMD EPYC 9554 (single NUMA node) |
| **NUMA Nodes** | 1 node — simpler but less sealing throughput |
| **Memory** | 256 GB DDR5 (all local to the single socket) |
| **GPU** | 1× NVIDIA RTX 4090 |
| **Notes** | NUMA configuration still relevant if SNC (Sub-NUMA Clustering) is enabled |

### Memory Population Rules

For optimal NUMA performance, memory must be **balanced across all sockets**:

```
✅ CORRECT: 256 GB per node
   Node 0: 8× 32GB DIMMs
   Node 1: 8× 32GB DIMMs
   
❌ WRONG: All memory on one node
   Node 0: 16× 32GB DIMMs
   Node 1: none (all access goes through interconnect)
```

Check your motherboard manual for the correct DIMM population order.

---

## Checking Your NUMA Topology

### 1. Basic NUMA Information

```bash
# Check number of NUMA nodes
numactl --hardware

# Sample output:
# available: 2 nodes (0-1)
# node 0 cpus: 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 64 65 66 67 68 69 70 71 72 73 74 75 76 77 78 79
# node 0 size: 257731 MB
# node 0 free: 241029 MB
# node 1 cpus: 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 80 81 82 83 84 85 86 87 88 89 90 91 92 93 94 95
# node 1 size: 257847 MB
# node 1 free: 242013 MB
# node distances:
# node   0   1
#   0:  10  21
#   1:  21  10
```

**Understanding the output:**
- `nodes`: Number of NUMA nodes (typically equals number of CPU sockets)
- `node N cpus`: CPUs belonging to that node
- `node N size`: Memory local to that node
- `node distances`: `10` = local, `20+` = remote. Lower is better.

### 2. Detailed NUMA Visualization

```bash
# Install lstopo
sudo apt install hwloc

# Visual NUMA topology
lstopo --of png > numa-topology.png

# Text-based topology
lstopo --of txt

# Sample output (simplified):
# Machine (1007GB total)
#   Package L#0 (AMD EPYC 9554)
#     NUMANode L#0 (P#0 local=257731MB)
#     L3 L#0 (32MB)
#       Core L#0 (P#0)
#         PU L#0 (P#0)
#         PU L#1 (P#64)
#       ...
#   Package L#1 (AMD EPYC 9554)
#     NUMANode L#1 (P#1 local=257847MB)
#     L3 L#0 (32MB)
#       Core L#0 (P#16)
#         PU L#0 (P#16)
#         PU L#1 (P#80)
#       ...
```

### 3. Quick Command Reference

```bash
# Count NUMA nodes
lscpu | grep "NUMA node(s)" | awk '{print $3}'

# CPU-to-NUMA mapping
lscpu | grep "NUMA node[0-9]"

# Memory per node
numastat -c -m | head -20

# See which node a specific process is using
numastat -p <PID>

# Continuous NUMA monitoring
watch -n 2 numastat
```

---

## BIOS Configuration

NUMA configuration starts in the BIOS/UEFI. These settings vary by motherboard vendor.

### AMD Systems (EPYC)

| Setting | Recommended Value | Notes |
|---------|:-----------------:|-------|
| **NUMA Nodes per Socket (NPS)** | **NPS1** or **NPS2** | NPS1 = single NUMA node per socket. NPS2 = better memory bandwidth isolation. |
| **Memory Interleaving** | **Disabled** | Allows each socket to use its local memory first |
| **SR-IOV Support** | Enabled | For GPU passthrough if using VMs |
| **Above 4G Decoding** | Enabled | Required for multiple GPUs |
| **Resizable BAR** | Enabled | Improves GPU performance for sealing |

**NPS (NUMA Nodes per Socket) Comparison:**

| Setting | NUMA Nodes | Use Case |
|---------|:----------:|----------|
| NPS0 | 1 (whole system is one node) | Simple but loses NUMA benefits |
| NPS1 | 2 (one per socket) | **Recommended** — balances complexity and performance |
| NPS2 | 4 (two per socket) | Maximum isolation, higher complexity |
| NPS4 | 8 (four per socket) | Extreme isolation, not recommended for Filecoin |

### Intel Systems (Xeon)

| Setting | Recommended Value | Notes |
|---------|:-----------------:|-------|
| **Sub-NUMA Clustering (SNC)** | **Enabled** | Similar to NPS2, splits each socket into 2 nodes |
| **Memory Interleaving** | Disabled | Keep memory local per socket |
| **Cluster-on-Die** | Auto | Let firmware decide optimal split |
| **SR-IOV** | Enabled | For GPU passthrough |

### Setting NUMA in BIOS (General Steps)

1. Enter BIOS (F2/Del during boot)
2. Navigate to **Advanced > AMD CBS** (AMD) or **Advanced > Memory Configuration** (Intel)
3. Find `NUMA Nodes per Socket` or `Sub-NUMA Clustering`
4. Set to desired value
5. Save and reboot
6. Verify with `numactl --hardware`

---

## Linux NUMA Configuration

### 1. Enable NUMA in the Kernel

NUMA is enabled by default in most modern Linux kernels. Verify:

```bash
# Check if NUMA is enabled in kernel
dmesg | grep -i numa

# Expected output:
# [    0.000000] NUMA: Initialized NUMA topology (2 nodes)
# [    0.000000] NUMA: Node 0 [mem 0x00000000-0x9fffffff] + [mem 0x100000000-0x44ffffffff] -> [mem 0x00000000-0x44ffffffff]
# [    0.000000] NUMA: Node 1 [mem 0x450000000-0x88ffffffff] -> [mem 0x450000000-0x88ffffffff]

# If NUMA is disabled, add to kernel boot parameters:
# Edit /etc/default/grub
# GRUB_CMDLINE_LINUX="numa=on"
# Then: sudo update-grub && sudo reboot
```

### 2. Install NUMA Tools

```bash
sudo apt update
sudo apt install -y numactl linux-tools-common linux-tools-$(uname -r)
```

### 3. Configure Process/Thread Binding

#### Method A: numactl (Recommended for Lotus)

Use `numactl` to bind Lotus processes to specific NUMA nodes:

```bash
# Bind lotus-worker to NUMA node 0
numactl --cpunodebind=0 --membind=0 lotus-worker run

# Bind a second worker to NUMA node 1
numactl --cpunodebind=1 --membind=1 lotus-worker run
```

#### Method B: taskset (CPU-only binding, no memory guarantee)

```bash
# Bind to specific CPU cores (0-31)
taskset -c 0-31 lotus-worker run
```

#### Method C: cgroups (Advanced)

```bash
# Create cgroup for NUMA node 0
sudo cgcreate -g cpuset,memory:/lotus-numa0

# Assign CPUs from node 0
sudo cgset -r cpuset.cpus=0-15,64-79 lotus-numa0

# Assign memory node 0
sudo cgset -r cpuset.mems=0 lotus-numa0

# Run lotus-worker in this cgroup
sudo cgexec -g cpuset,memory:/lotus-numa0 lotus-worker run
```

### 4. Persistent Configuration (systemd)

Create systemd service files for NUMA-aware Lotus workers:

```ini
# /etc/systemd/system/lotus-worker@.service
[Unit]
Description=Lotus Worker on NUMA node %i
After=network.target

[Service]
Type=simple
ExecStart=/usr/bin/numactl --cpunodebind=%i --membind=%i /usr/local/bin/lotus-worker run
Restart=on-failure
RestartSec=30
User=lotus
Group=lotus

# NUMA-specific memory limits
MemoryMax=200G

[Install]
WantedBy=multi-user.target
```

Enable and start workers:

```bash
sudo systemctl daemon-reload
sudo systemctl enable lotus-worker@0
sudo systemctl enable lotus-worker@1
sudo systemctl start lotus-worker@0
sudo systemctl start lotus-worker@1
```

### 5. Kernel Tuning for NUMA

```bash
# /etc/sysctl.d/99-numa.conf

# Keep processes on their assigned NUMA node (don't auto-migrate)
kernel.numa_balancing = 0

# Reduce page reclaim tendencies
vm.swappiness = 10

# Keep more dentry/inode cache (benefits frequent file access)
vm.vfs_cache_pressure = 50
```

Apply kernel parameters:

```bash
sudo sysctl --system
```

---

## Lotus-Specific NUMA Optimization

### Scenario 1: Single Lotus Worker per NUMA Node

This is the **recommended configuration** for maximum throughput.

```bash
# Node 0 worker (handles sectors 1-500)
numactl --cpunodebind=0 --membind=0 \
  lotus-worker run \
  --worker-repo=/mnt/nvme0/lotus-worker \
  --listen=0.0.0.0:3457

# Node 1 worker (handles sectors 501-1000)
numactl --cpunodebind=1 --membind=1 \
  lotus-worker run \
  --worker-repo=/mnt/nvme1/lotus-worker \
  --listen=0.0.0.0:3458
```

### Scenario 2: Single Lotus Node with NUMA-Aware Memory

If using a single Lotus node (not separate workers):

```bash
# Run lotus daemon with memory interleaved (uses all nodes)
# Daemon is not NUMA-sensitive
lotus daemon

# Run lotus-miner bound to node 0 (where GPU is)
numactl --cpunodebind=0 --membind=0 lotus-miner run
```

### Scenario 3: NVIDIA GPU NUMA Affinity

GPUs can be associated with NUMA nodes. This is crucial for WindowPoST performance.

```bash
# Check GPU NUMA affinity
nvidia-smi topo -m

# Sample output:
#         GPU0    GPU1    CPU Affinity    NUMA Affinity
# GPU0     X      PHB     0-15,64-79      0
# GPU1    PHB      X      16-31,80-95     1

# In this example:
# - GPU0 is on NUMA node 0 (CPUs 0-15, 64-79)
# - GPU1 is on NUMA node 1 (CPUs 16-31, 80-95)
```

Map workers to GPU-affine NUMA nodes:

```bash
# Worker 0 uses GPU0 and NUMA node 0
numactl --cpunodebind=0 --membind=0 \
  lotus-worker run \
  --worker-repo=/mnt/nvme0/lotus-worker

# Worker 1 uses GPU1 and NUMA node 1  
numactl --cpunodebind=1 --membind=1 \
  lotus-worker run \
  --worker-repo=/mnt/nvme1/lotus-worker
```

### Scenario 4: Dynamic Load Balancing

For variable workloads, use `numad` for automatic NUMA balancing:

```bash
# Install numad
sudo apt install numad

# Start numad daemon
sudo systemctl enable --now numad

# Monitor its decisions
sudo numad -f /var/log/numad.log
```

> **⚠️ Caution**: `numad` can interfere with manual numactl bindings. Use EITHER manual binding OR `numad`, not both.

---

## GPU and NUMA Affinity

### Identifying GPU-to-NUMA Topology

```bash
# Detailed GPU topology
nvidia-smi topo -m

# PCIe bus info for each GPU
nvidia-smi --query-gpu=index,pci.bus_id,name --format=csv

# Map PCIe bus to NUMA node
for gpu in $(nvidia-smi --query-gpu=index --format=csv,noheader); do
    bus=$(nvidia-smi -i $gpu --query-gpu=pci.bus_id --format=csv,noheader)
    numa_node=$(cat /sys/bus/pci/devices/0000:${bus}/numa_node 2>/dev/null)
    echo "GPU $gpu (PCI $bus) → NUMA node $numa_node"
done
```

### Optimal GPU Assignment

```bash
#!/bin/bash
# gpu-numa-affinity.sh - Bind GPU memory and worker to same NUMA node

GPU_NODE_0=$(cat /sys/bus/pci/devices/0000:$(nvidia-smi -i 0 --query-gpu=pci.bus_id --format=csv,noheader | tr -d ' ')/numa_node)
GPU_NODE_1=$(cat /sys/bus/pci/devices/0000:$(nvidia-smi -i 1 --query-gpu=pci.bus_id --format=csv,noheader | tr -d ' ')/numa_node)

echo "GPU 0 → NUMA node $GPU_NODE_0"
echo "GPU 1 → NUMA node $GPU_NODE_1"

# Start worker on GPU0's NUMA node
numactl --cpunodebind=$GPU_NODE_0 --membind=$GPU_NODE_0 \
    lotus-worker run --worker-repo=/mnt/nvme0/lotus-worker &
    
# Start worker on GPU1's NUMA node
numactl --cpunodebind=$GPU_NODE_1 --membind=$GPU_NODE_1 \
    lotus-worker run --worker-repo=/mnt/nvme1/lotus-worker &

wait
```

### Multi-GPU NUMA Considerations

| GPU Configuration | NUMA Strategy |
|-------------------|---------------|
| **1 GPU** | Bind to GPU's NUMA node. All sealing on that node. |
| **2 GPUs, each on different nodes** | **Ideal.** One worker per GPU per node. |
| **2 GPUs on same node** | Both GPUs share the same NUMA node. Use `NVIDIA_VISIBLE_DEVICES` to split. |
| **4 GPUs across 2 nodes** | 2 GPUs per node. Two workers per node, each pinned to one GPU. |

Split GPUs when multiple share a node:

```bash
# Worker 0 uses GPU 0
CUDA_VISIBLE_DEVICES=0 numactl --cpunodebind=0 --membind=0 \
    lotus-worker run --worker-repo=/mnt/nvme0/lotus-worker &

# Worker 1 uses GPU 1
CUDA_VISIBLE_DEVICES=1 numactl --cpunodebind=0 --membind=0 \
    lotus-worker run --worker-repo=/mnt/nvme0/lotus-worker &
```

---

## Verifying NUMA Configuration

### 1. Check Process Binding

```bash
# Find lotus process PIDs
pgrep -a lotus-worker

# Check NUMA binding of a specific PID
numastat -p <PID>

# Sample output:
# Per-node process memory usage (in MBs) for PID 12345 (lotus-worker)
# Node 0 Node 1 Total
# ------ ------ -----
# 52341.23 234.56 52575.79
#
# If Node 1 is near-zero → binding is working correctly
```

### 2. Verify Memory Allocation

```bash
# System-wide NUMA memory stats
numastat -m

# Sample output:
#                          Node 0    Node 1
#                 Total  257.1 Gi  257.8 Gi
#                Used    189.2 Gi   45.1 Gi
#                Free     67.9 Gi  212.7 Gi
#
# Node 1 is underutilized → need to start more workers on it
```

### 3. Performance Comparison

Run a quick benchmark to validate NUMA effectiveness:

```bash
# Test with NUMA binding
numactl --cpunodebind=0 --membind=0 lotus-worker run &
sleep 10
# Check seal performance in lotus-miner info

# Test without NUMA binding (for comparison)
lotus-worker run &
sleep 10
# Compare APY (seals per day)
```

### 4. Monitoring NUMA Events

```bash
# Watch NUMA miss events (shows remote memory access)
watch -n 5 'numastat -v | grep -E "(miss|Node|local|remote)"'

# High remote access ratio (>10%) indicates NUMA misconfiguration
# Expected: >90% local access, <10% remote

# Check cross-socket interconnect utilization
sudo apt install -y perf
perf stat -e "node-store-misses,node-load-misses" -a -- sleep 10
```

### 5. Validation Checklist

```markdown
- [ ] numactl --hardware shows correct NUMA nodes
- [ ] nvidia-smi topo -m shows expected GPU-to-NUMA mapping
- [ ] lotus-worker processes are bound to specific NUMA nodes
- [ ] Remote memory access is <10% (check with numastat)
- [ ] Memory is balanced across DIMM slots per node
- [ ] BIOS NPS/SNC setting matches intended configuration
- [ ] systemd service files are configured with NUMA bindings
- [ ] GPU and worker are on the same NUMA node
- [ ] numad is disabled when using manual bindings
```

---

## Common Pitfalls & Troubleshooting

### ❌ All memory allocated to one node

**Symptom**: `numastat -m` shows one node has 90%+ of memory usage.
**Cause**: Workers are not bound to different NUMA nodes.
**Fix**: Start multiple workers with `--cpunodebind=N` for each node.

### ❌ High remote memory access (>20%)

**Symptom**: `numastat -v | grep remote` shows high numbers.
**Cause**: Processes not bound, or memory interleaving enabled in BIOS.
**Fix**: 
```bash
# Check and fix
numastat -v | grep -i remote
# Should be <10% of local+miss total
# Fix: apply numactl bindings to all lotus processes
```

### ❌ WindowPoST failures on multi-GPU systems

**Symptom**: Random WindowPoST deadline misses.
**Cause**: WindowPoST process running on wrong NUMA node for the GPU.
**Fix**:
```bash
# Run WindowPoST on the same node as the GPU handling proofs
numactl --cpunodebind=0 --membind=0 lotus-miner proving compute window-post <deadline>
```

### ❌ NUMA balancing overhead

**Symptom**: CPU usage spikes every few seconds without clear cause.
**Cause**: Kernel NUMA balancing (auto_migrate) moving pages between nodes.
**Fix**: 
```bash
echo 0 | sudo tee /proc/sys/kernel/numa_balancing
# Or persist: add 'kernel.numa_balancing = 0' to /etc/sysctl.d/99-numa.conf
```

### ❌ SNC (Sub-NUMA Clustering) confusion

**Symptom**: `numactl --hardware` shows 4+ nodes but only 2 physical sockets.
**Cause**: SNC is enabled, splitting each socket into 2 nodes.
**Fix**: 
- Either disable SNC for simpler management (NPS1 equivalent)
- Or embrace it and bind workers to the 4 sub-nodes
```bash
# For 4 NUMA nodes with SNC:
numactl --cpunodebind=0 --membind=0 lotus-worker run &
numactl --cpunodebind=1 --membind=1 lotus-worker run &
numactl --cpunodebind=2 --membind=2 lotus-worker run &
numactl --cpunodebind=3 --membind=3 lotus-worker run &
```

### ❌ Virtual machine NUMA issues

**Symptom**: Poor performance despite correct guest NUMA config.
**Cause**: Hypervisor not exposing NUMA topology to the VM.
**Fix**:
- **VMware**: Set `numa.autosize.cookie` and `numa.vcpu.preferHT=true`
- **KVM/QEMU**: Use `<numa>` in domain XML to expose topology
- **Proxmox**: Enable `NUMA` in VM options

### ❌ NUMA binding conflicts with Docker

**Symptom**: Docker container ignores numactl.
**Cause**: Docker runs with unrestricted cgroups that override NUMA.
**Fix**:
```bash
# Pass numactl inside the container:
docker run --privileged \
  --cpuset-cpus="0-15,64-79" \
  --memory="200g" \
  --gpus '"device=0"' \
  lotus-worker
```

---

## Reference Cards

### Quick Command Card

```text
┌───────────────────────────────────────────────────────────────┐
│                  NUMA COMMAND REFERENCE                       │
├───────────────────────────────────────────────────────────────┤
│ numactl --hardware        Show NUMA topology                  │
│ numactl --cpunodebind=N   Bind to CPUs on node N              │
│ numactl --membind=N       Allocate memory from node N only    │
│ numactl -m N -C N <cmd>  Combined CPU+memory binding          │
│ numastat                  System NUMA memory stats             │
│ numastat -p <PID>         Process NUMA memory distribution    │
│ numastat -v               Verbose stats (remote/local access) │
│ lstopo                    Visual NUMA topology                │
│ lscpu | grep NUMA         CPU-to-NUMA mapping                 │
│ nvidia-smi topo -m        GPU-to-NUMA topology                │
│ dmesg | grep -i numa      Kernel NUMA initialization          │
└───────────────────────────────────────────────────────────────┘
```

### Critical BIOS Settings

```text
┌───────────────────────────────────────────────────────────────┐
│              BIOS NUMA SETTINGS (AMD EPYC)                    │
├───────────────────────────────────────────────────────────────┤
│ NUMA Nodes per Socket  → NPS1 or NPS2                        │
│ Memory Interleaving    → Disabled                             │
│ SR-IOV Support         → Enabled                              │
│ Above 4G Decoding      → Enabled                              │
│ Resizable BAR          → Enabled                              │
└───────────────────────────────────────────────────────────────┘
```

---

## References & Further Reading

- [Linux NUMA Documentation](https://www.kernel.org/doc/html/latest/admin-guide/numa.html)
- [numactl Manual](https://man7.org/linux/man-pages/man8/numactl.8.html)
- [NVIDIA GPU NUMA Affinity](https://docs.nvidia.com/deploy/pdf/NUMA_affinity.pdf)
- [AMD EPYC NUMA Optimization](https://www.amd.com/en/developer/epyc-optimization-guide.html)
- [Filecoin Lotus Worker Configuration](https://lotus.filecoin.io/storage-providers/advanced-configurations/seal-workers/)

---

*This tutorial is part of the Filecoin Storage Provider Bounty Program. For corrections or updates, please open a PR or issue.*

*Part of the [Storage Provider Bounty Program](https://github.com/filecoin-project/community/blob/main/storage-provider-bounty-program/README.md)*
