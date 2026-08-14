## Ahmet Barış Günaydın

Independent researcher and full-stack consultant. I write WGSL by hand and ship
browser-native research artifacts — things you open in a tab, with no install,
no server and no API key. Two Zenodo preprints; every artifact ships the code
that measured it.

### What I've built

Cited work first — released, DOI-archived, and validated against an external reference.

| | |
|---|---|
| [**zero-tvm**](https://github.com/abgnydn/zero-tvm) · [zerotvm.com](https://zerotvm.com) · [DOI](https://doi.org/10.5281/zenodo.20838918) | Ten models on hand-written WGSL, from Phi-3-mini up to a 35B sparse mixture-of-experts that no compiler stack ships a build of. Benchmarked against WebLLM on identical weights in the same session, every number in `BENCH.md`. Peer weight-sharing over WebRTC and pipeline splitting across two tabs. |
| [**webgpu-dna**](https://github.com/abgnydn/webgpu-dna) · [webgpudna.com](https://webgpudna.com) · [DOI](https://doi.org/10.5281/zenodo.20506339) | The CNRS/IN2P3 Geant4-DNA Monte Carlo toolkit in a browser. Electron track structure, Karamitros IRT radiolysis, SSB/DSB scoring on a B-DNA fibre grid — validated against a Geant4 11.4.1 ntuple across eight energies, with the failed experiments committed beside the passing ones. |
| [**webgpu-q**](https://github.com/abgnydn/webgpu-q) · [live](https://webgpu-q.vercel.app) · [DOI](https://doi.org/10.5281/zenodo.20494382) | Quantum many-body and chemistry — statevector and MPS, plus HF/UHF, DFT, MP2, CCSD, CCSD(T) and EOM-CCSD, cross-checked against PySCF, ITensor and brute-force EOM. A six-level research ladder with fidelity pass bars and seeded RNG. |
| [**neuropulse**](https://github.com/abgnydn/neuropulse) · [neuropulse.live](https://neuropulse.live) · [DOI](https://doi.org/10.5281/zenodo.20505470) | A full Phi-3-mini forward pass rendered 1:1 from live activations — 3.8B parameters, 11 WGSL kernels, 292 dispatches per token. Every glow is a real tensor read back off the GPU. |
| [**webgpu-kernel-fusion**](https://github.com/abgnydn/webgpu-kernel-fusion) · [kernelfusion.dev](https://kernelfusion.dev) · [DOI](https://doi.org/10.5281/zenodo.19331833) | The research line: two preprints on single-kernel fusion for GPU compute, measured across CUDA, WebGPU, JAX/XLA and Triton with a CI-gated equivalence check between implementations. |
| [**iz**](https://github.com/abgnydn/iz) · [DOI](https://doi.org/10.5281/zenodo.20496086) | Per-facility CO₂ benchmark for Turkish CBAM-scope industry. A closed-form physics baseline against the EU CBAM default, validated on EUTL-verified plants under leave-one-plant-out. |
| [**gpubench**](https://github.com/abgnydn/gpubench) · [gpubench.dev](https://gpubench.dev) | WebGPU compute benchmarks on visitors' hardware. Six workloads across eight GPU vendors; the run table is published as a [dataset](https://huggingface.co/datasets/abgunaydin/webgpu-compute-benchmarks). |

Shipped products, on their own release cadence.

| | |
|---|---|
| [**markview**](https://github.com/abgnydn/markview) · [markview.ai](https://markview.ai) | Local-first Markdown editor. Web app plus desktop builds for macOS, Windows and Linux. |
| [**nib**](https://github.com/abgnydn/nib) | Local-first grammar and writing assistant for macOS. Native overlay across every app, Harper rules plus a bundled on-device model, no account. |
| [**webgpu-fly**](https://github.com/abgnydn/webgpu-fly) · [live](https://webgpu-fly.pages.dev) | Realtime LIF simulation of the FlyWire fruit-fly connectome, the MANC spine and a MuJoCo body — 139,255 neurons, ~15M synaptic edges. |

Earlier and experimental — live, but each carries its own caveats in its README.

[enter-the-painting](https://huggingface.co/spaces/abgunaydin/enter-the-painting) lifts any image into a 3D Gaussian-splat cloud, fully client-side ·
[draw-instant](https://github.com/abgnydn/draw-instant) runs Stable Diffusion in the browser, with the all-our-kernels path still being extended to the U-Net ·
[fused-lora](https://fused-lora.pages.dev) fine-tunes BitNet b1.58 in a tab and emits ~4 MB `.flora` adapters ·
[wgpu-adas-bench](https://github.com/abgnydn/wgpu-adas-bench) fuses an 11-stage ADAS pipeline into one `wgpu-native` dispatch ·
[safenpm](https://safenpm.dev) scans `npm install` for typosquats and risky postinstall scripts, pre-release ·
[dimples](https://dimples.pages.dev) is a golf game where you are the ball

### Reach

- Email: **hi [at] barisgunaydin.com**
- Personal site: [barisgunaydin.com](https://barisgunaydin.com)
- HuggingFace: [@abgunaydin](https://huggingface.co/abgunaydin) — models, Spaces, and the [WebGPU compute benchmark dataset](https://huggingface.co/datasets/abgunaydin/webgpu-compute-benchmarks)
- X: [@abgnydn_](https://x.com/abgnydn_)
- Location: Chiang Mai, Thailand (UTC+7)
