## Ahmet Barış Günaydın

Independent researcher in Chiang Mai. **WebGPU kernels, browser-native ML, kernel fusion across domains.** I write WGSL by hand, measure on real devices, and ship the artifacts as web pages people can open without installing anything.

The thesis the work below shares: **per-dispatch overhead is the dominant tax on browser GPU compute, and most workloads — RL, transformer inference, radiobiology Monte Carlo, quantum simulation — collapse from "needs a server" to "runs in a browser tab" once you fuse the loop.** Two preprints, one open SDK, 592 real devices tested.

---

### Featured work

| | |
|---|---|
| [**zero-tvm**](https://github.com/abgnydn/zero-tvm) ([zerotvm.com](https://zerotvm.com)) | Phi-3-mini running in a browser on **10 hand-written WGSL kernels** (27 files, 3,078 LOC). ~40 tok/s on M2 Pro — **22% behind WebLLM's TVM-autotuned 85 kernels** on identical weights. The gap is 22% and not 2× because for decoder-only LLMs the compiler's complexity budget mostly isn't buying anything. |
| [**webgpu-kernel-fusion**](https://github.com/abgnydn/webgpu-kernel-fusion) ([kernelfusion.dev](https://kernelfusion.dev)) | The research umbrella + paper. **720× over PyTorch CUDA** on Tesla T4 (Acrobot). **159× over PyTorch MPS** on M2 Pro (financial sim). Confirmed across CUDA, WebGPU, JAX/XLA, Triton — **the fusion advantage is GPU-API-agnostic.** [DOI: 10.5281/zenodo.19342888](https://doi.org/10.5281/zenodo.19342888) |
| [**webgpu-fusion-max**](https://github.com/abgnydn/webgpu-fusion-max) | Pushing single-dispatch fusion to a real model. **Phi-3-mini 3.6B at 2.2 tok/s in Chrome** via tiled FFN + tiled attention. The "how far does it scale" companion to zero-tvm. |
| [**gpubench**](https://github.com/abgnydn/gpubench) ([gpubench.dev](https://gpubench.dev)) | Real WebGPU compute benchmarks running on your hardware. **592 devices tested** across 7 GPU vendors. 6 workloads — Rastrigin, N-body, Acrobot-v1, MountainCar-v0, CartPole-v1, Monte Carlo Pi. The crowd-sourced confirmation surface for the kernel-fusion claims. |
| [**wgpu-adas-bench**](https://github.com/abgnydn/wgpu-adas-bench) | Full ADAS sensor fusion pipeline — 11 stages fused into a single GPU dispatch via wgpu-native. **12-15× over PyTorch** on the same GPU. 1 dispatch vs 11. |
| [**webgpu-dna**](https://github.com/abgnydn/webgpu-dna) ([webgpudna.com](https://webgpudna.com)) | WebGPU port of CNRS/IN2P3's **Geant4-DNA** Monte Carlo toolkit for radiobiology. CSDA range matches Geant4-DNA reference within 1.5%, energy conservation 100%, 46/46 unit tests pass. Karamitros 2011 IRT chemistry runs in a Web Worker. |
| [**webgpu-q**](https://webgpu-q.vercel.app) | Quantum circuit simulator (statevector + MPS) targeting 70+ qubits via WebGPU. Six-level research ladder with formal experimental protocol — fidelity pass bars, seeded RNG, honest negative results committed as JSON. |
| [**markview**](https://github.com/abgnydn/markview) ([markview.ai](https://markview.ai)) | Embeddable Markdown rendering stack — React SDK, Web Component, 23 MCP tools, native macOS app. GitHub-flavored + Mermaid + KaTeX + Shiki. AGPL-3.0. |

### Skills I'm hireable for

- WebGPU compute pipelines, hand-written WGSL, kernel fusion
- Browser-native LLM inference (Phi-3, Llama, BitNet) — quantization, KV cache, attention variants
- `wgpu-native` (Rust) for cross-platform GPU code without browser overhead
- GPU performance measurement at scale (Cloudflare-native data collection from 592+ devices)
- Migrating compute-heavy workloads from PyTorch / Triton / JAX to WebGPU/WGSL with measured speedups

If you're building consumer AI that pushes inference to the client, ADAS / robotics perception teams measuring sensor-fusion latency, or research groups wanting a browser-native simulator for a domain (chemistry, biology, physics), I'm available for **consulting and contract work**.

### Reach me

- Email: **abgunaydin94 [at] gmail.com**
- Personal site: [barisgunaydin.com](https://barisgunaydin.com)
- Location: Chiang Mai, Thailand (UTC+7)

<sub>Profile last updated 2026-05-04. The work above is what's currently shipped or measurable; older repos and forks are kept for archaeological purposes only.</sub>
