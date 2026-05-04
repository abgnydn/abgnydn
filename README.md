## Ahmet Barış Günaydın

**Senior full-stack consultant by day. Independent researcher by night.** Currently consulting on the dotstudio platform at Publicis Media (via bi:procsi / Azendo). In off-hours I write WGSL by hand and ship browser-native research artifacts you can open without installing anything.

Seven small research projects shipped in six weeks of evenings. Two Zenodo preprints. The shape of the work is the same in both modes: pick a real problem, ship a real artifact, measure on real hardware.

### The thesis the research below shares

Per-dispatch overhead is the dominant tax on browser GPU compute. Most workloads — RL, transformer inference, radiobiology Monte Carlo, quantum simulation — collapse from "needs a server" to "runs in a browser tab" once you fuse the loop into a single dispatch. The numbers vary by hardware and workload; what's stable is the qualitative shape, the cross-API confirmation (CUDA, WebGPU, JAX/XLA, Triton via [`@wgpu-fusion/core`](https://github.com/abgnydn/webgpu-kernel-fusion)), and the reproducibility — every artifact ships its measurement code so you can re-run on your own GPU.

### Featured work

| | |
|---|---|
| **[zero-tvm](https://github.com/abgnydn/zero-tvm)** · [zerotvm.com](https://zerotvm.com) | Phi-3-mini running in a browser on ten hand-written WGSL kernel roles, replacing the 85 autotuned shaders WebLLM's compiler emits. Whether you can match an autotuner with hand-written code at this scale is the open question; this is a data point. |
| **[webgpu-kernel-fusion](https://github.com/abgnydn/webgpu-kernel-fusion)** · [kernelfusion.dev](https://kernelfusion.dev) | The research umbrella and paper. Single-kernel fusion measured across CUDA, WebGPU, JAX/XLA, and Triton — the fusion advantage is GPU-API-agnostic, not Apple-Silicon-specific. [DOI: 10.5281/zenodo.19342888](https://doi.org/10.5281/zenodo.19342888) |
| **[webgpu-fusion-max](https://github.com/abgnydn/webgpu-fusion-max)** | The "how far does single-dispatch scale?" experiment. Tiled FFN and tiled attention pushing fused decoding up to a real Phi-3-mini-3.6B forward pass. The opposite-extreme companion to zero-tvm's 10-kernel design. |
| **[neuropulse.live](https://neuropulse.live)** | The visualization companion to zero-tvm. The same Phi-3-mini forward pass, rendered tensor by tensor on a WebGPU canvas — every glow is a live activation read-back from the GPU. Zero server, zero API key, your browser. |
| **[gpubench](https://github.com/abgnydn/gpubench)** · [gpubench.dev](https://gpubench.dev) | Live WebGPU compute benchmarks running on visitors' hardware. Six standard workloads — Rastrigin, N-body, Acrobot-v1, MountainCar-v0, CartPole-v1, Monte Carlo Pi. The crowd-sourced confirmation surface for the kernel-fusion claims. |
| **[wgpu-adas-bench](https://github.com/abgnydn/wgpu-adas-bench)** | Full ADAS sensor fusion pipeline — 11 stages fused into one GPU dispatch via `wgpu-native`. Same one-dispatch pattern, applied to automotive perception. |
| **[webgpu-dna](https://github.com/abgnydn/webgpu-dna)** · [webgpudna.com](https://webgpudna.com) | The CNRS/IN2P3 Geant4-DNA Monte Carlo toolkit ported to WebGPU. Electron tracks, IRT chemistry in a Web Worker, SSB/DSB scoring on a B-DNA fiber grid — validated against published Geant4-DNA reference numbers. |
| **[webgpu-q](https://webgpu-q.vercel.app)** | Quantum circuit simulator (statevector + MPS) targeting 70+ qubits in a browser tab. Six-level research ladder with a formal experimental protocol — fidelity pass bars, seeded RNG, honest negative results committed as JSON. |
| **[markview](https://github.com/abgnydn/markview)** · [markview.ai](https://markview.ai) | Embeddable Markdown rendering stack — React SDK, Web Component, native macOS app, MCP integration for AI assistants. The shippable-product side of the portfolio. |

### Available for hire

Two modes — pick whichever fits your problem:

- **Senior full-stack consulting** — TypeScript / Next.js / Node / databases / SDK design / monorepo wrangling / production shipping. Default mode; what most clients actually need.
- **WebGPU & browser-native ML** — WGSL by hand, kernel fusion, on-device LLM inference, custom compute pipelines, `wgpu-native` (Rust) for cross-platform GPU code without browser overhead. The niche.

Neither side has been the bottleneck on any of the projects above.

### Reach

- Email: **abgunaydin94 [at] gmail.com**
- Personal site: [barisgunaydin.com](https://barisgunaydin.com)
- Location: Chiang Mai, Thailand (UTC+7)

<sub>Profile reflects what's currently shipped. Numbers move; the qualitative shape doesn't.</sub>
