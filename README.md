## Ahmet Barış Günaydın

**Senior full-stack consultant by day. Independent researcher by night.** Currently consulting on the dotstudio platform at Publicis Media (via bi:procsi / Azendo). In off-hours I write WGSL by hand and ship browser-native research artifacts you can open without installing anything.

Two Zenodo preprints and a set of browser-native research artifacts. The shape of the work is the same in both modes: pick a real problem, ship a real artifact, measure on real hardware.

### The thesis the research below shares

Per-dispatch overhead dominates one specific shape: a long sequential loop where each step is cheap and depends on the previous one. Fusing that into a single dispatch is worth 7.2× over JAX/XLA at 1,500 timesteps and narrows to 1.29× at 500 — the advantage scales with episode length, and it is measured the same way across CUDA, WebGPU, JAX/XLA and Triton.

It is not a general result, and the boundaries are the interesting part. JAX GPU beats hand-fused WebGPU 6.8× on embarrassingly parallel Rastrigin. Against a properly batched baseline, crowd-sourced data across eight GPU vendors has fusion losing by 3–7×. And in a whole pipeline the gain dilutes to whatever fraction is actually fusable: webgpu-dna's fused phase is 40× faster in isolation and 2% of the runtime, so end-to-end it is 1.48×.

Every artifact ships its measurement code, and the falsified experiments are committed next to the ones that worked.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/abgnydn/abgnydn/main/assets/fusion-boundary-dark.svg">
  <img alt="Measured speedup of single-dispatch fusion against each named baseline, on a log scale. Wins: 94x vs per-step PyTorch CUDA on a 1,500-step financial simulation, 40x for webgpu-dna's fused phase in isolation, 13.5x for the native ADAS pipeline over a multi-kernel baseline, 7.8x crowd-sourced against per-step across 380 runs and 8 GPU vendors, 7.2x over JAX/XLA lax.scan. Marginal: 1.48x for webgpu-dna end-to-end, 1.29x over JAX on Acrobot-v1 at 500 steps. Losses: 0.30x against a batched baseline in the same crowd-sourced runs, 0.146x against JAX on parallel Rastrigin." src="https://raw.githubusercontent.com/abgnydn/abgnydn/main/assets/fusion-boundary-light.svg" width="100%">
</picture>

### Featured work

| | |
|---|---|
| **[zero-tvm](https://github.com/abgnydn/zero-tvm)** · [zerotvm.com](https://zerotvm.com) | Ten models running in a browser on hand-written WGSL, from Phi-3-mini up to a 35B sparse MoE that no compiler stack ships a build of. On Phi-3, measured against WebLLM on identical weights in the same session: 69.55 tok/s against 59.95 on an M2 Max. The 35B build has no A/B baseline because WebLLM ships no version of that model. Whether hand-written code can match an autotuner at this scale is the open question; this is a data point. |
| **[webgpu-kernel-fusion](https://github.com/abgnydn/webgpu-kernel-fusion)** · [kernelfusion.dev](https://kernelfusion.dev) | The research umbrella and paper. Single-kernel fusion measured across CUDA, WebGPU, JAX/XLA and Triton with a CI-gated equivalence check between implementations. The advantage is not Apple-Silicon-specific, and it is also not general — the same paper reports JAX GPU winning on parallel workloads. [DOI: 10.5281/zenodo.19331833](https://doi.org/10.5281/zenodo.19331833) |
| **[webgpu-fusion-max](https://github.com/abgnydn/webgpu-fusion-max)** | The "how far does single-dispatch scale?" experiment. Tiled FFN and tiled attention pushing fused decoding up to Phi-3-sized runs, which is where register and workgroup pressure start to bind. The opposite-extreme companion to zero-tvm's 10-kernel design. |
| **[neuropulse.live](https://neuropulse.live)** | The visualization companion to zero-tvm. The same Phi-3-mini forward pass, rendered tensor by tensor on a WebGPU canvas — every glow is a live activation read-back from the GPU. Zero server, zero API key, your browser. |
| **[gpubench](https://github.com/abgnydn/gpubench)** · [gpubench.dev](https://gpubench.dev) | Live WebGPU compute benchmarks on visitors' hardware. Six workloads — Rastrigin, N-body, Acrobot-v1, MountainCar-v0, CartPole-v1, Monte Carlo Pi — across eight GPU vendors. It tests the fusion claims rather than confirming them: the per-step arm reproduces a 7–12× win and the batched arm comes back at 0.15–0.39×, which is the result that bounds the thesis. Snapshot published as a [dataset](https://huggingface.co/datasets/abgunaydin/webgpu-compute-benchmarks). |
| **[wgpu-adas-bench](https://github.com/abgnydn/wgpu-adas-bench)** | Full ADAS sensor-fusion pipeline — 11 stages in one GPU dispatch via `wgpu-native`, 12–15× over the multi-kernel baseline on the same workload. The one-dispatch pattern outside the browser, where the comparison is not confounded by browser overhead. |
| **[webgpu-dna](https://github.com/abgnydn/webgpu-dna)** · [webgpudna.com](https://webgpudna.com) | The CNRS/IN2P3 Geant4-DNA Monte Carlo toolkit ported to WebGPU. Electron tracks, IRT chemistry in a Web Worker, SSB/DSB scoring on a B-DNA fiber grid, validated against a Geant4 11.4.1 ntuple. Tracking alone is ~241× Geant4 single-thread; end-to-end like-for-like is 1.48×, because the radiolysis phase cannot be fused and dominates. Both numbers are in the README, and the second is the honest one. |
| **[webgpu-q](https://webgpu-q.vercel.app)** | Quantum many-body and chemistry simulator in a browser tab — statevector and MPS, plus HF/UHF, DFT, MP2, CCSD, CCSD(T) and EOM-CCSD, cross-checked against PySCF and ITensor. A research ladder with a formal protocol: fidelity pass bars, seeded RNG, honest negative results committed as JSON. |
| **[markview](https://github.com/abgnydn/markview)** · [markview.ai](https://markview.ai) | Embeddable Markdown rendering stack — React SDK, Web Component, native macOS app, MCP integration for AI assistants. The shippable-product side of the portfolio. |

### Available for hire

Two modes — pick whichever fits your problem:

- **Senior full-stack consulting** — TypeScript / Next.js / Node / databases / SDK design / monorepo wrangling / production shipping. Default mode; what most clients actually need.
- **WebGPU & browser-native ML** — WGSL by hand, kernel fusion, on-device LLM inference, custom compute pipelines, `wgpu-native` (Rust) for cross-platform GPU code without browser overhead. The niche.

Neither side has been the bottleneck on any of the projects above.

### Reach

- Email: **hi [at] barisgunaydin.com**
- Personal site: [barisgunaydin.com](https://barisgunaydin.com)
- HuggingFace: [@abgunaydin](https://huggingface.co/abgunaydin) — models, Spaces, and the [WebGPU compute benchmark dataset](https://huggingface.co/datasets/abgunaydin/webgpu-compute-benchmarks)
- X: [@abgnydn_](https://x.com/abgnydn_)
- Location: Chiang Mai, Thailand (UTC+7)

<sub>Profile reflects what's currently shipped. Numbers move; the qualitative shape doesn't.</sub>
