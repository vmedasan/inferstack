# Development Environment

This document records the initial local development environment used for InferStack.

## Host Hardware

- Operating system: Windows 11 Home
- CPU: AMD Ryzen 9 5900HX
- CPU cores: 8 physical / 16 logical
- System memory: approximately 32 GB
- GPU: NVIDIA GeForce RTX 3070 Laptop GPU
- GPU memory: 8 GB VRAM
- NVIDIA Windows driver: 610.60
- Windows driver-reported CUDA capability: 13.3

## Linux Development Environment

InferStack development is performed primarily inside WSL2 using Ubuntu.

- Distribution: Ubuntu 24.04.5 LTS
- Architecture: x86_64
- Kernel: 5.15.167.4-microsoft-standard-WSL2
- Init system: systemd
- WSL-visible memory: approximately 15 GiB
- Swap: 4 GiB
- Initial Linux filesystem free space: approximately 955 GB

Projects are stored in the native WSL filesystem under:

`~/code`

rather than the Windows-mounted `/mnt/c` filesystem.

## Verified Base Tooling

The initial environment includes:

- Git
- GitHub CLI
- GCC / build-essential
- curl
- wget
- jq
- tree

Python, Go, Docker Engine, Kubernetes tooling, OpenTofu, and GPU compute support will be configured and verified separately as the project progresses.

## GPU Validation Status

The NVIDIA GPU and Windows driver have been verified using `nvidia-smi` from Windows.

The following have NOT yet been validated inside WSL:

- PyTorch CUDA support
- CUDA development tooling
- GPU-enabled containers
- vLLM GPU inference
- NVIDIA Container Toolkit

No GPU benchmark results will be published until these are explicitly validated.

## Reproducibility Policy

Performance results published by InferStack should include, where applicable:

- hardware configuration
- operating system and kernel
- relevant software versions
- model name and revision
- inference engine version
- precision or quantization configuration
- batch size
- concurrency
- test duration
- warmup methodology
- raw benchmark results

Performance claims should be backed by enough information to reproduce or reasonably validate the experiment.
