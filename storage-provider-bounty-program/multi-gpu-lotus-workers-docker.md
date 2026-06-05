# Run Lotus workers with multiple GPUs in Docker

This guide shows one way to run several `lotus-worker` processes on the same
Linux host, with each worker pinned to a different Nvidia GPU. It is written for
storage providers who already have a synced Lotus node and an initialized
`lotus-miner`, and want Docker to keep worker dependencies, environment
variables, and GPU assignment repeatable.

The examples use two GPUs, but the same pattern works for more GPUs by adding
one service, one sealing path, and one worker name per GPU.

## Target hardware

A practical production host for this layout has:

- Linux with Docker Engine 19.03 or newer.
- Nvidia driver and Nvidia Container Toolkit installed on the host.
- Two or more Nvidia GPUs. Use GPUs with enough VRAM for the tasks they will
  receive. Lotus documentation lists 5 GiB VRAM for PreCommit2 and 11 GiB VRAM
  for Commit2 on 32 GiB sectors.
- At least 128 GiB RAM for one active 32 GiB-sector GPU worker, more if the host
  will run multiple PC2/C2 jobs at once.
- Fast NVMe-backed paths for sealing storage, proof parameters, and parent
  cache. Proof parameters for 32 GiB sectors require more than 100 GiB, and the
  parent cache should also be on fast local storage.
- A trusted private network path from the worker containers to the miner API.

Avoid mixing AMD and Nvidia GPUs on the same worker host. Lotus documentation
notes that mixed GPU vendors can cause OpenCL issues, and Nvidia currently has
the better-supported storage-provider path.

## Host preparation

Install and verify the Nvidia runtime before starting Lotus containers:

```bash
nvidia-smi -L
docker run --rm --gpus all nvidia/cuda:12.4.1-base-ubuntu22.04 nvidia-smi
```

Create persistent paths for proof parameters and one sealing path per GPU:

```bash
sudo mkdir -p /srv/filecoin/{parameters,parent-cache}
sudo mkdir -p /srv/filecoin/seal/{gpu0,gpu1}
sudo chown -R "$USER":"$USER" /srv/filecoin
```

The sealing paths should be separate fast disks or separate high-throughput
mounts. Sharing one slow disk between several GPU workers can make the disk the
bottleneck and remove the benefit of parallel GPUs.

## Miner setup

The miner must accept worker API connections on a trusted interface. Do not
expose the miner API port to the public internet.

In the miner config, set `ListenAddress` and `RemoteListenAddress` to a private
LAN address or to the host address used by the worker containers. Then get a
worker token:

```bash
lotus-miner auth api-info --perm admin
```

Save the returned value in a local `.env` file that is not committed to source
control:

```bash
MINER_API_INFO=<token>:/ip4/<miner-api-private-ip>/tcp/<port>/http
```

If you want the GPU workers to own PC2/C2 work, reduce overlapping work on the
miner itself. In the miner `config.toml`, use the `[Storage]` section to disable
the phases delegated to workers, for example:

```toml
[Storage]
  AllowPreCommit2 = false
  AllowCommit = false
```

Keep WindowPoST resources protected. If the miner and worker containers share
one host, reserve enough CPU, RAM, and GPU capacity for proving deadlines.

## Worker image

Build Lotus from a known release tag rather than from the development branch.
Update `LOTUS_REF` when upgrading the storage provider stack.

```dockerfile
# Dockerfile.lotus-worker
FROM nvidia/cuda:12.4.1-devel-ubuntu22.04 AS build

ARG GO_VERSION=1.25.7
ARG LOTUS_REF=v1.36.0

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
      ca-certificates build-essential git curl jq pkg-config clang make \
      hwloc libhwloc-dev ocl-icd-opencl-dev opencl-headers && \
    rm -rf /var/lib/apt/lists/*

RUN curl -fsSL "https://go.dev/dl/go${GO_VERSION}.linux-amd64.tar.gz" \
      | tar -xz -C /usr/local
ENV PATH="/usr/local/go/bin:${PATH}"

WORKDIR /src
RUN git clone --depth 1 --branch "${LOTUS_REF}" \
      https://github.com/filecoin-project/lotus.git
WORKDIR /src/lotus
RUN make clean all && make install

FROM nvidia/cuda:12.4.1-runtime-ubuntu22.04

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
      ca-certificates jq hwloc ocl-icd-libopencl1 libhwloc15 libnuma1 && \
    rm -rf /var/lib/apt/lists/*

COPY --from=build /usr/local/bin/lotus /usr/local/bin/lotus
COPY --from=build /usr/local/bin/lotus-miner /usr/local/bin/lotus-miner
COPY --from=build /usr/local/bin/lotus-worker /usr/local/bin/lotus-worker

ENV FIL_PROOFS_USE_GPU_COLUMN_BUILDER=1
ENV FIL_PROOFS_USE_GPU_TREE_BUILDER=1
ENV FIL_PROOFS_USE_MULTICORE_SDR=1
ENV FIL_PROOFS_PARAMETER_CACHE=/var/lib/filecoin/parameters
ENV FIL_PROOFS_PARENT_CACHE=/var/lib/filecoin/parent-cache
ENV NVIDIA_DRIVER_CAPABILITIES=compute,utility

ENTRYPOINT ["lotus-worker"]
```

Build it:

```bash
docker build -f Dockerfile.lotus-worker \
  --build-arg LOTUS_REF=v1.36.0 \
  -t local/lotus-worker:v1.36.0 .
```

## Compose layout

The Compose file below runs two GPU workers. Each worker:

- uses host networking so `MINER_API_INFO` can point at the miner API exactly as
  it would from the host;
- receives only one GPU through `NVIDIA_VISIBLE_DEVICES`;
- mounts separate worker repo and sealing paths;
- shares read/write proof parameter and parent-cache mounts;
- starts only PC2/C2 tasks with `--no-default --precommit2 --commit`.

```yaml
# docker-compose.workers.yml
services:
  worker-gpu0:
    image: local/lotus-worker:v1.36.0
    network_mode: host
    runtime: nvidia
    restart: unless-stopped
    env_file: .env
    environment:
      LOTUS_WORKER_NAME: docker-gpu0
      NVIDIA_VISIBLE_DEVICES: "0"
      NVIDIA_DRIVER_CAPABILITIES: compute,utility
      FIL_PROOFS_PARAMETER_CACHE: /var/lib/filecoin/parameters
      FIL_PROOFS_PARENT_CACHE: /var/lib/filecoin/parent-cache
      FIL_PROOFS_USE_GPU_COLUMN_BUILDER: "1"
      FIL_PROOFS_USE_GPU_TREE_BUILDER: "1"
      FIL_PROOFS_USE_MULTICORE_SDR: "1"
      PC2_32G_MAX_CONCURRENT: "1"
      C2_32G_MAX_CONCURRENT: "1"
    command: ["run", "--no-default", "--precommit2", "--commit"]
    ulimits:
      nofile:
        soft: 1048576
        hard: 1048576
    volumes:
      - worker-gpu0:/root/.lotusworker
      - /srv/filecoin/parameters:/var/lib/filecoin/parameters
      - /srv/filecoin/parent-cache:/var/lib/filecoin/parent-cache
      - /srv/filecoin/seal/gpu0:/var/lib/filecoin/seal

  worker-gpu1:
    image: local/lotus-worker:v1.36.0
    network_mode: host
    runtime: nvidia
    restart: unless-stopped
    env_file: .env
    environment:
      LOTUS_WORKER_NAME: docker-gpu1
      NVIDIA_VISIBLE_DEVICES: "1"
      NVIDIA_DRIVER_CAPABILITIES: compute,utility
      FIL_PROOFS_PARAMETER_CACHE: /var/lib/filecoin/parameters
      FIL_PROOFS_PARENT_CACHE: /var/lib/filecoin/parent-cache
      FIL_PROOFS_USE_GPU_COLUMN_BUILDER: "1"
      FIL_PROOFS_USE_GPU_TREE_BUILDER: "1"
      FIL_PROOFS_USE_MULTICORE_SDR: "1"
      PC2_32G_MAX_CONCURRENT: "1"
      C2_32G_MAX_CONCURRENT: "1"
    command: ["run", "--no-default", "--precommit2", "--commit"]
    ulimits:
      nofile:
        soft: 1048576
        hard: 1048576
    volumes:
      - worker-gpu1:/root/.lotusworker
      - /srv/filecoin/parameters:/var/lib/filecoin/parameters
      - /srv/filecoin/parent-cache:/var/lib/filecoin/parent-cache
      - /srv/filecoin/seal/gpu1:/var/lib/filecoin/seal

volumes:
  worker-gpu0:
  worker-gpu1:
```

If your Docker setup does not use `runtime: nvidia`, replace it with the GPU
syntax supported by your Compose version, or launch with `docker run --gpus`.
Docker supports selecting a specific GPU by index or UUID, for example
`--gpus '"device=0,2"'`.

## Start and attach sealing storage

Start the workers:

```bash
docker compose -f docker-compose.workers.yml up -d
```

Attach each container's sealing directory once:

```bash
docker compose -f docker-compose.workers.yml exec worker-gpu0 \
  lotus-worker storage attach --init --seal /var/lib/filecoin/seal

docker compose -f docker-compose.workers.yml exec worker-gpu1 \
  lotus-worker storage attach --init --seal /var/lib/filecoin/seal
```

After the first attach, restart the services so the workers begin with their
storage path already registered:

```bash
docker compose -f docker-compose.workers.yml restart
```

## Verify the deployment

Check that each container sees only its assigned GPU:

```bash
docker compose -f docker-compose.workers.yml exec worker-gpu0 nvidia-smi -L
docker compose -f docker-compose.workers.yml exec worker-gpu1 nvidia-smi -L
```

Check miner-side registration and task limits:

```bash
lotus-miner sealing workers
lotus-miner storage list
```

The worker list should show `docker-gpu0` and `docker-gpu1`, their task limits,
and their GPU status. If both containers see the same GPU, prefer GPU UUIDs over
numeric IDs in `NVIDIA_VISIBLE_DEVICES`, because PCI ordering can change after
driver or hardware changes.

## Operating notes

- Keep `.env` outside version control. The miner API token grants administrative
  access to sealing operations.
- Keep the miner API on a private interface or host-only network. Do not publish
  it to the internet.
- Pin Lotus releases across the miner and workers. Upgrade the image, miner, and
  worker containers together when the network requires a Lotus upgrade.
- Start with `PC2_32G_MAX_CONCURRENT=1` and `C2_32G_MAX_CONCURRENT=1` per GPU.
  Increase only after watching GPU memory, RAM, disk I/O, and WindowPoST
  deadlines during a real sealing window.
- For PC1-heavy workers, create separate CPU-oriented containers with
  `--no-default --precommit1` and do not assign GPUs to them. PC1 is write-heavy
  and benefits more from CPU, RAM, and NVMe isolation than from GPU access.
- If a worker must be stopped, use `docker compose stop <service>` and confirm
  `lotus-miner sealing workers` no longer assigns it work before removing its
  storage path.

## Troubleshooting

- Worker fails to start with file descriptor errors: confirm the container
  `nofile` ulimit is `1048576` and the host allows the same limit.
- `nvidia-smi` is unavailable in the container: confirm Nvidia Container Toolkit
  is installed and `NVIDIA_DRIVER_CAPABILITIES` includes `utility`.
- Worker connects but does not take PC2/C2 tasks: check
  `lotus-miner sealing workers`, worker command flags, and the
  `PC2_32G_MAX_CONCURRENT` / `C2_32G_MAX_CONCURRENT` settings.
- Workers fight over one GPU: use GPU UUIDs from `nvidia-smi -L` instead of
  numeric indexes.
- Sealing slows down as more workers are added: check NVMe utilization, proof
  parameter/cache path latency, RAM pressure, and WindowPoST resource
  contention.
- Worker cannot connect to miner: verify `MINER_API_INFO`, miner
  `ListenAddress` / `RemoteListenAddress`, firewall rules, and API reachability
  from the host network namespace.

## References

- [Lotus seal workers](https://lotus.filecoin.io/storage-providers/seal-workers/seal-workers/)
- [Lotus hardware requirements](https://lotus.filecoin.io/storage-providers/get-started/hardware-requirements/)
- [Lotus storage-provider prerequisites](https://lotus.filecoin.io/storage-providers/setup/prerequisites/)
- [Docker GPU access](https://docs.docker.com/engine/containers/gpu/)
- [Nvidia Container Toolkit Docker runtime](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/1.10.0/runtime/docker.html)
- [Lotus source repository](https://github.com/filecoin-project/lotus)
