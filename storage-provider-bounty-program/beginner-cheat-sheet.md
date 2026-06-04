# Filecoin Storage Provider — Beginner Cheat Sheet

> A quick-start guide for new storage providers joining the Filecoin network.
> Last updated: June 2026

---

## Table of Contents

1. [What is a Filecoin Storage Provider?](#what-is-a-filecoin-storage-provider)
2. [Minimum Requirements & Eligibility](#minimum-requirements--eligibility)
3. [Hardware Configuration by Budget](#hardware-configuration-by-budget)
4. [Software Setup](#software-setup)
5. [Key Lotus Commands](#key-lotus-commands)
6. [WindowPoST Basics](#windowpost-basics)
7. [Common Pitfalls & Troubleshooting](#common-pitfalls--troubleshooting)
8. [Useful Resources](#useful-resources)

---

## What is a Filecoin Storage Provider?

A **Storage Provider** (formerly called "miner") is a participant in the Filecoin network who:

- Rents out disk space to clients
- Stores client data in sealed sectors
- Proves they are storing data correctly (via Proof-of-Spacetime)
- Earns **FIL** tokens as reward

Filecoin uses a **blockchain** to track deals, storage proofs, and payments. The reference implementation is **[Lotus](https://github.com/filecoin-project/lotus)**.

---

## Minimum Requirements & Eligibility

### 10 TiB Minimum

To participate as a storage provider, you **must have at least 10 TiB of committed storage capacity**. This is the minimum sector size requirement enforced by the network.

### Network Requirements

| Requirement | Minimum |
|-------------|---------|
| Public IP | Required (static preferred) |
| Bandwidth | 100 Mbps symmetric (1 Gbps recommended) |
| Latency | < 50 ms to Filecoin nodes |

### Software Requirements

- **OS**: Ubuntu 22.04+ or Debian 12 (recommended)
- **Filecoin Implementation**: Lotus (most popular), Venus (pool-friendly), Forest (Rust), Fuhon (C++)
- **Required Dependencies**: Go 1.21+, Rust, GCC, Git, jq, hwloc, OpenCL

---

## Hardware Configuration by Budget

### 🟢 Budget Setup (~$3,000–$5,000)

*Ideal for testing / small-scale starting*

| Component | Specification |
|-----------|---------------|
| CPU | AMD Ryzen 9 7950X (16C/32T) or Intel i9-14900K |
| RAM | 128 GB DDR5 |
| Storage (Seal) | 2× NVMe SSD 2 TB (RAID 0) |
| Storage (Store) | 2× HDD 16 TB (for long-term storage) |
| GPU | NVIDIA RTX 4090 (24 GB VRAM) — **required for sealing** |
| Network | 1 Gbps NIC |

**Estimated daily seal rate**: ~50–80 GiB/day

### 🟡 Mid-Range Setup (~$8,000–$12,000)

| Component | Specification |
|-----------|---------------|
| CPU | AMD Threadripper PRO 7965WX (24C/48T) |
| RAM | 256 GB DDR5 ECC |
| Storage (Seal) | 3× NVMe SSD 4 TB (RAID 0) |
| Storage (Store) | 4× HDD 20 TB |
| GPU | 2× NVIDIA RTX 4090 or 1× RTX 6000 Ada |
| Network | 10 Gbps NIC |

**Estimated daily seal rate**: ~200–400 GiB/day

### 🔴 High-End / Enterprise Setup ($25,000+)

| Component | Specification |
|-----------|---------------|
| CPU | 2× AMD EPYC 9654 (192C/384T total) |
| RAM | 512 GB – 1 TB DDR5 ECC |
| Storage (Seal) | 6× NVMe SSD 8 TB |
| Storage (Store) | 12× HDD 20 TB (JBOD or RAID) |
| GPU | 4× NVIDIA RTX 4090 |
| Network | 25 Gbps NIC + dual power supply |

**Estimated daily seal rate**: 1+ TiB/day

> **💡 Tip**: GPU is the bottleneck for sealing. More GPUs = faster sealing.

---

## Software Setup

### 1. Install Lotus

```bash
# Install dependencies
sudo apt update && sudo apt install -y mesa-opencl-icd ocl-icd-opencl-dev \
  gcc git bzr jq pkg-config curl clang build-essential \
  hwloc libhwloc-dev wget

# Install Go 1.21+
wget -c https://go.dev/dl/go1.21.5.linux-amd64.tar.gz
sudo rm -rf /usr/local/go && sudo tar -C /usr/local -xzf go1.21.5.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin
echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc

# Build Lotus
git clone https://github.com/filecoin-project/lotus.git
cd lotus
git checkout releases
make clean all
sudo make install

# Verify installation
lotus version
```

### 2. Initialize your storage provider

```bash
# Start the Lotus daemon
lotus daemon &

# Wait for chain sync (this can take hours)
lotus sync wait

# Create a new wallet
lotus wallet new bls
# Save the address — this is your owner address

# Send FIL to your wallet for initial pledge
# (Get FIL from an exchange or faucet)

# Initialize the miner actor
lotus-miner init \
  --owner=<YOUR_WALLET_ADDRESS> \
  --sector-size=32GiB \
  --worker=<YOUR_WALLET_ADDRESS>
```

### 3. Start the miner

```bash
# Start the miner
lotus-miner run &

# Check miner info
lotus-miner info

# Check sector status
lotus-miner sectors list
```

---

## Key Lotus Commands

### Wallet & Account

```bash
lotus wallet list                    # List all wallets
lotus wallet balance <address>       # Check FIL balance
lotus wallet new bls                 # Create new BLS wallet
lotus wallet new secp256k1           # Create new secp256k1 wallet
lotus send <to> <amount>             # Send FIL
```

### Mining / Storage Providing

```bash
lotus-miner info                     # Overview of miner status
lotus-miner sectors list             # List all sectors
lotus-miner sectors status <id>      # Check specific sector
lotus-miner proving info             # View proving deadlines
lotus-miner proving faults           # List faulty sectors
lotus-miner storage list             # List storage paths
lotus-miner storage find <sector>    # Find sector location
lotus-miner sealing workers          # List sealing workers
```

### Chain & Synchronization

```bash
lotus sync status                    # Check sync progress
lotus sync wait                      # Wait for full sync
lotus chain head                     # Show current chain height
lotus chain getblock <cid>           # Get block details
lotus state power                    # View network power
lotus state miner-power <addr>       # Your miner power
```

### Deals

```bash
lotus-miner deals list               # List all deals
lotus-miner deals list --completed   # Completed deals
lotus-miner deals import <cid>       # Import a deal
lotus client list-deals              # List client deals
lotus client query-ask <miner>       # Query storage price
```

---

## WindowPoST Basics

**WindowPoST** (Proof-of-Spacetime) is a periodic proof that you are still storing your sectors.

### How it works

- Every **24 hours**, the network divides into **48 windows** (30 minutes each)
- Each window requires you to prove a subset of your sectors
- You must submit a proof **before the window expires**
- **Failure = Fault** → penalty fees (up to ~3.5 days of block reward per sector)

### Key parameters

| Parameter | Value |
|-----------|-------|
| Proving period | 24 hours (2880 epochs) |
| Windows per period | 48 |
| Challenge window | 30 minutes (60 epochs) |
| Max sectors per partition | 2,349 (for 32 GiB sectors) |

### Monitoring WindowPoST

```bash
# Check current proving deadlines
lotus-miner proving info

# View deadline schedule
lotus-miner proving deadlines

# Manually submit WindowPoST (if needed)
lotus-miner proving compute window-post <deadline>

# Check for faults
lotus-miner proving faults
```

### Common WindowPoST issues

| Issue | Symptom | Solution |
|-------|---------|----------|
| Slow GPU | Proof not submitted in time | Upgrade GPU / reduce sectors per deadline |
| Disk I/O bottleneck | Proof computation slow | Use faster NVMe for sector storage |
| Network latency | Submission timeout | Ensure < 50 ms latency to nodes |
| OOM (Out of Memory) | Process crashes | Increase RAM or swap space |

---

## Common Pitfalls & Troubleshooting

### ❌ Chain never syncs
**Fix**: Check your network connection. Use `lotus sync status` to see progress. First sync can take 6–24+ hours. Consider using a snapshot:

```bash
# Download a chain snapshot (much faster)
lotus chain export --tipset @latest --recent-stateroots=2000 snapshot.car
# Or use a pre-built snapshot:
wget https://snapshots.filops.net/minimal/latest.car
lotus daemon --import-snapshot latest.car
```

### ❌ Sealing is too slow
**Fix**: GPU is the bottleneck. Check:
- `lotus-miner sealing workers` — are all workers busy?
- GPU temperature — thermal throttling?
- `lotus-miner info` — is the miner actively sealing?

### ❌ WindowPoST keeps failing
**Fix**: 
- `lotus-miner proving faults` — check which sectors
- Ensure you have enough free RAM during WindowPoST
- Move sectors to faster storage if possible

### ❌ Low storage power
**Fix**: 
- Check `lotus-miner info` for power
- Ensure your sector quality multiplier is optimized (verified deals > CC sectors)
- More committed capacity = more power

### ❌ Deal proposals get rejected
**Fix**:
- Check `lotus-miner deals list` for failures
- Ensure your collateral is sufficient
- Verify your asking price `lotus client query-ask <miner>`

---

## Useful Resources

| Resource | Link |
|----------|------|
| Lotus Documentation | https://lotus.filecoin.io |
| Filecoin Spec | https://spec.filecoin.io |
| Network Stats | https://filscan.io |
| Filecoin Slack | https://filecoin.io/slack |
| Filecoin Community | https://github.com/filecoin-project/community |
| Venus (Pool Mining) | https://venus.filecoin.io |
| Filecoin Snapshots | https://snapshots.filops.net |
| Storage Provider WG | https://github.com/filecoin-project/community/labels/category%3A%20storage-provider-working-group |

---

## Quick Reference Card

```
┌─────────────────────────────────────────────────────────┐
│                  QUICK COMMANDS                          │
├─────────────────────────────────────────────────────────┤
│ lotus daemon &              Start the daemon            │
│ lotus sync wait             Wait for sync               │
│ lotus-miner run &           Start the miner             │
│ lotus-miner info            Check everything            │
│ lotus-miner sectors list    List all sectors            │
│ lotus-miner proving info    Check WindowPoST status     │
│ lotus wallet balance <addr> Check FIL balance           │
│ lotus-miner sealing workers Check sealing progress      │
└─────────────────────────────────────────────────────────┘
```

---

*This cheat sheet is maintained by the community. For corrections or updates, please open a PR or issue.*

*Part of the Filecoin Storage Provider Bounty Program —* [Learn more](https://github.com/filecoin-project/community/blob/main/storage-provider-bounty-program/README.md)
