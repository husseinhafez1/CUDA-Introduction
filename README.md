# CUDA & GPU Programming - Getting Started

Based on [UPenn CIS 5650](https://cis5650-fall-2025.github.io/) materials.

## Setup
- Windows 11
- NVIDIA RTX 2070 Max-Q (CUDA 13.3)
- Visual Studio 2026

## What I built

### CUDA + OpenGL Interop
A CUDA kernel that writes directly into an OpenGL texture via a PBO. The window shows the GPU's compute capability as colors — top half major version, bottom half minor.

### CUDA Introduction Exercises

**SAXPY** — `z = a * x + y`. Straightforward once you understand that cudaMalloc takes bytes, not elements. Wasted time on that.

**Matrix Transpose** — copy kernel first, then transpose. The index math (`index_out = i * sizeY + j`) looks obvious in hindsight.

**Matrix Multiplication** — naive matmul with 16×16 thread blocks, one output element per thread. Took a while to get the indexing consistent between the CPU reference and the GPU kernel.