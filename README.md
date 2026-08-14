## Ahmet Barış Günaydın

Independent researcher and full-stack consultant. I write WGSL by hand and ship
browser-native research artifacts — things you open in a tab, with no install,
no server and no API key. Two Zenodo preprints; every artifact ships the code
that measured it.

### What I've built

Eleven of these are live right now. Open any of them.

**Language models in the browser**

| | |
|---|---|
| [**zero-tvm**](https://github.com/abgnydn/zero-tvm) · [zerotvm.com](https://zerotvm.com) | Ten models on hand-written WGSL, from Phi-3-mini up to a 35B sparse mixture-of-experts that no compiler stack ships a build of. Peer weight-sharing over WebRTC and pipeline splitting across two tabs. |
| [**neuropulse**](https://github.com/abgnydn/neuropulse) · [neuropulse.live](https://neuropulse.live) | A full 3.8B forward pass rendered 1:1 from live activations. Every glow is a real tensor read back off the GPU. |
| [**fused-lora**](https://github.com/abgnydn/fused-lora) · [live](https://fused-lora.pages.dev) | LoRA fine-tuning of BitNet b1.58 in a browser tab. GPU AdamW, ~86 ms/step, adapters out as 4 MB `.flora` files. |

**Science, ported to the GPU**

| | |
|---|---|
| [**webgpu-dna**](https://github.com/abgnydn/webgpu-dna) · [webgpudna.com](https://webgpudna.com) | The CNRS/IN2P3 Geant4-DNA Monte Carlo toolkit in a browser. Electron track structure, Karamitros IRT radiolysis, SSB/DSB scoring on a B-DNA fibre grid, validated against a Geant4 11.4.1 ntuple. |
| [**webgpu-q**](https://github.com/abgnydn/webgpu-q) · [live](https://webgpu-q.vercel.app) | Quantum many-body and chemistry — statevector and MPS, plus HF/UHF, DFT, MP2, CCSD, CCSD(T) and EOM-CCSD, cross-checked against PySCF and ITensor. |
| [**webgpu-fly**](https://github.com/abgnydn/webgpu-fly) · [live](https://webgpu-fly.pages.dev) | Realtime LIF simulation of the FlyWire fruit-fly connectome, the MANC spine and a MuJoCo body. ~140k neurons, ~15M edges. |
| [**iz**](https://github.com/abgnydn/iz) | Per-facility CO₂ benchmark for Turkish CBAM-scope industry. A closed-form physics baseline against the EU CBAM default, validated against EUTL-verified plants. |

**Graphics and generative**

| | |
|---|---|
| [**enter-the-painting**](https://huggingface.co/spaces/abgunaydin/enter-the-painting) | Any image lifted into a 3D Gaussian-splat cloud, fully client-side. Depth Anything v2/v3 plus SlimSAM, nothing uploaded. |
| [**draw-instant**](https://github.com/abgnydn/draw-instant) | Realtime Stable Diffusion with a fused U-Net pass — attention, conv, groupnorm and time embedding in one kernel. |
| [**dimples**](https://dimples.pages.dev) | You are the golf ball, trying to get hit. WebGPU with a WebGL2 fallback. |

Several of these share a research line — single-kernel fusion on GPU compute, written up in two preprints. The measurements, the protocols and the experiments that failed all live in the repos.

**Measurement and tooling**

| | |
|---|---|
| [**gpubench**](https://github.com/abgnydn/gpubench) · [gpubench.dev](https://gpubench.dev) | WebGPU compute benchmarks on visitors' hardware. Six workloads, eight GPU vendors, [published as a dataset](https://huggingface.co/datasets/abgunaydin/webgpu-compute-benchmarks). |
| [**webgpu-kernel-fusion**](https://github.com/abgnydn/webgpu-kernel-fusion) · [kernelfusion.dev](https://kernelfusion.dev) | The research line and two preprints. [DOI](https://doi.org/10.5281/zenodo.19331833) |
| [**wgpu-adas-bench**](https://github.com/abgnydn/wgpu-adas-bench) | ADAS sensor fusion, 11 stages in one `wgpu-native` dispatch. The same pattern outside the browser. |
| [**markview**](https://github.com/abgnydn/markview) · [markview.ai](https://markview.ai) | Local-first Markdown editor. React SDK, Web Component, Tauri desktop app, MCP integration. |
| [**safenpm**](https://github.com/abgnydn/safenpm) · [safenpm.dev](https://safenpm.dev) | Drop-in `npm install` that sandboxes postinstall scripts and catches typosquats before they run. |
| [**nib**](https://github.com/abgnydn/nib) | Local-first grammar and writing assistant for macOS. Native overlay, on-device model, no account. |

### Reach

- Email: **hi [at] barisgunaydin.com**
- Personal site: [barisgunaydin.com](https://barisgunaydin.com)
- HuggingFace: [@abgunaydin](https://huggingface.co/abgunaydin) — models, Spaces, and the [WebGPU compute benchmark dataset](https://huggingface.co/datasets/abgunaydin/webgpu-compute-benchmarks)
- X: [@abgnydn_](https://x.com/abgnydn_)
- Location: Chiang Mai, Thailand (UTC+7)
