<h1 align="center">Clark &nbsp;·&nbsp; IN3RT1A</h1>

<p align="center"><b>Systems engineer. Distributed ML infrastructure, real-time networking, game technology, and Lean 4 formal verification.</b></p>

<p align="center">
  <a href="https://github.com/xaviercallens/HiveMind/pulls?q=is%3Apr+author%3Aclark719664"><img alt="HiveMind PRs" src="https://img.shields.io/badge/HiveMind-29%20PRs%20%C2%B7%2015%20merged-1f6feb?style=for-the-badge&logo=github&logoColor=white"></a>
  <a href="https://github.com/xaviercallens/HiveMind/blob/main/lean4/HiveMindSpec.lean"><img alt="Lean 4" src="https://img.shields.io/badge/Lean%204-machine--checked%20proofs-6f42c1?style=for-the-badge"></a>
  <a href="https://github.com/clark719664/pc-tv-apps/releases/latest"><img alt="Apps" src="https://img.shields.io/badge/IN3RT1A%20apps-Windows%20%2B%20Linux-2ea043?style=for-the-badge"></a>
  <a href="https://payhip.com/IN3RT1A"><img alt="Payhip" src="https://img.shields.io/badge/Store-payhip.com%2FIN3RT1A-f5b700?style=for-the-badge"></a>
</p>

> I ship working code with tests, and I don't let a claim stand that the code can't back up. Every number on this page links to the commit, PR or release that proves it.

---

## At a glance

| | |
|---|---|
| **Upstream pull requests** | **16 merged** (15 on [HiveMind](https://github.com/xaviercallens/HiveMind/pulls?q=is%3Apr+author%3Aclark719664+is%3Amerged), 1 on [Protocol-Canary](https://github.com/StellarCanary/Protocol-Canary/pull/570)) and **14 more in review**, all CI-green |
| **Standing on HiveMind** | Named **code owner** for 11 subsystem paths and listed maintainer-track co-owner (*"Grandmaster Core & Formal Architect"*) in [GOVERNANCE.md](https://github.com/xaviercallens/HiveMind/blob/main/GOVERNANCE.md) |
| **Formal verification** | Lean 4 proofs merged upstream; the spec now carries **77 machine-checked theorems** (0 `sorry`, 0 user axioms, audited in CI) |
| **Shipped products** | **4 desktop apps** for Windows and Linux, released with checksums and bundled-tool sources on every build |
| **In the browser** | [Lucent](https://clark719664.github.io/lucent/), a GPU path tracer, and [Synapse](https://clark719664.github.io/synapse/), an OpenTelemetry trace explorer, both live on GitHub Pages |
| **Specialities** | QUIC 0-RTT · STUN/TURN · Mixture-of-Experts routing · FP8/INT4 kernels · error-feedback compression · Soroban smart contracts · Unreal 5 / Godot 4 |

---

## Featured work

### 🧠 Distributed ML infrastructure — [xaviercallens/HiveMind](https://github.com/xaviercallens/HiveMind)

An open-source framework that trains a community-owned Sparse Mixture-of-Experts model across idle consumer GPUs (DiLoCo + QLoRA + BOINC-style validation). My work runs from the wire to the proofs.

- **Transport:** async QUIC with 0-RTT resumption and WebSocket fallback ([#9](https://github.com/xaviercallens/HiveMind/pull/9)) → multi-node WAN NAT traversal with STUN/TURN and UDP hole-punching ([#22](https://github.com/xaviercallens/HiveMind/pull/22)) → a real QUIC 0-RTT + STUN/TURN implementation with live loopback tests ([#40](https://github.com/xaviercallens/HiveMind/pull/40)).
- **GPU kernels:** Triton `float8_e4m3fn` kernel and causal tree-attention mask ([#8](https://github.com/xaviercallens/HiveMind/pull/8)); INT4 + FP8 fused MoE router kernel with a benchmark ([#23](https://github.com/xaviercallens/HiveMind/pull/23)); double-buffered CUDA-stream expert prefetcher ([#7](https://github.com/xaviercallens/HiveMind/pull/7)).
- **Routing & compression (in review):** a 128-expert three-tier hierarchical router, 16 gating inner products per token instead of 128 ([#71](https://github.com/xaviercallens/HiveMind/pull/71)); token-tree speculative expert prefetch with a measured hit rate ([#75](https://github.com/xaviercallens/HiveMind/pull/75)); an error-feedback residual for Top-k + FP8 outer loops that beats the Top-5% baseline at 5.6× fewer bytes in the reproducible benchmark ([#63](https://github.com/xaviercallens/HiveMind/pull/63)), wired into the real worker upload path ([#69](https://github.com/xaviercallens/HiveMind/pull/69)).
- **Serving & platform:** SSE streaming on `/v1/chat/completions` ([#6](https://github.com/xaviercallens/HiveMind/pull/6)); domain-expert LoRA adapters with a Top-k FP8 content-addressed registry ([#25](https://github.com/xaviercallens/HiveMind/pull/25)); native `steam_api64` bridge ([#10](https://github.com/xaviercallens/HiveMind/pull/10)); real WebGL 3D geo-ring HUD ([#42](https://github.com/xaviercallens/HiveMind/pull/42)).
- **Protocol correctness:** TURN ChannelBind rewritten to RFC 5766 (client-chosen channel, implicit permission) ([#73](https://github.com/xaviercallens/HiveMind/pull/73)); federated workunits bound to their assignee so no node can consume another's job ([#72](https://github.com/xaviercallens/HiveMind/pull/72)).
- **Keeping it honest:** repaired the project's CI after an import cycle silently stopped collection ([#67](https://github.com/xaviercallens/HiveMind/pull/67)); replaced unmeasured speedups, synthetic results labelled as real and self-reported scores with measured values or explicit "not measured" labels, each guarded by tests ([#64](https://github.com/xaviercallens/HiveMind/pull/64), [#65](https://github.com/xaviercallens/HiveMind/pull/65), [#74](https://github.com/xaviercallens/HiveMind/pull/74), [#76](https://github.com/xaviercallens/HiveMind/pull/76), [#77](https://github.com/xaviercallens/HiveMind/pull/77)).

### 📐 Formal verification — Lean 4

- Proved prefix-trie speculative acceptance and RFC 9001 0-RTT bounds ([#21](https://github.com/xaviercallens/HiveMind/pull/21)).
- Reworked theorems so they prove properties of the **actual** protocols rather than restating their assumptions, and made the audit pipeline refuse to report an unchecked proof as verified ([#39](https://github.com/xaviercallens/HiveMind/pull/39), [#41](https://github.com/xaviercallens/HiveMind/pull/41)).
- In review ([#68](https://github.com/xaviercallens/HiveMind/pull/68)): the error-feedback update modelled in Lean with conservation for *any* compressor (including decay and clipping), the Top-k contraction rate `d·residual ≤ (d−k)·input`, bounded residuals under stale-step decay, and the deterministic half of the UCB1 bandit argument. All in core Lean, no Mathlib, because the upstream spec is deliberately dependency-free.

### 📺 Shipped products — IN3RT1A apps for Windows and Linux

Free apps that get your PC and your TVs working together, published at **[payhip.com/IN3RT1A](https://payhip.com/IN3RT1A)** with installers and Linux builds on **[pc-tv-apps](https://github.com/clark719664/pc-tv-apps)** and a home page at **[clark719664.github.io/pc-tv-apps](https://clark719664.github.io/pc-tv-apps/)**.

- **PC Cast Pro:** TV remote, casting from any link or embedded player, multicast to many TVs at once, your PC's video library, multi-screen grids and free live TV in one app.
- **PC Cast Lite:** the casting only. **PC TV Live:** free live TV by country with a guide, built on a documented legal-source filter. **PC TV Remote:** the remote only.
- One-click Windows installers with no administrator rights needed, Linux tarballs with a one-command install and optional systemd service, SHA-256 checksums and the corresponding source for bundled GPL tools on every [release](https://github.com/clark719664/pc-tv-apps/releases/latest). No ads; [donations from $1](https://payhip.com/b/Wn9fE) keep them free.

### 🌐 Live in the browser — Lucent and Synapse

Two zero-dependency TypeScript + WebGL2 apps with strict types, lint, tests and a GitHub Pages deploy in CI. Open them and they run, no install.

- **[Lucent](https://github.com/clark719664/lucent)** ([live demo](https://clark719664.github.io/lucent/)): a real-time progressive path tracer on the GPU. Drop in a glTF/GLB model and it renders with PBR textures, clearcoat, sheen and refractive glass, lit by importance-sampled HDRIs with multiple importance sampling. An edge-aware denoiser and temporal reprojection keep it clean while you orbit; the glTF parser, BVH builder and integrator are all written from scratch. About 49 kB gzipped.
- **[Synapse](https://github.com/clark719664/synapse)** ([live demo](https://clark719664.github.io/synapse/)): a zero-backend OpenTelemetry trace explorer. A live service map with requests flowing as particles, a span waterfall, import of OTLP/JSON, Jaeger and Zipkin traces, and a seeded 17-service simulator with four injectable incidents. About 21 kB gzipped.

### ⭐ Stellar & Soroban

- **[StellarCanary/Protocol-Canary](https://github.com/StellarCanary/Protocol-Canary):** `getHealth` RPC method support in the compatibility checker ([#570](https://github.com/StellarCanary/Protocol-Canary/pull/570), merged).
- **[CredenceOrg/Credence-Contracts](https://github.com/CredenceOrg/Credence-Contracts):** bounty-escrow contract entry points and paginated views in Rust/Soroban ([#1636](https://github.com/CredenceOrg/Credence-Contracts/pull/1636), in review).

---

## Also building

Work that is private or not yet released. Ask if you want a walkthrough.

- **Games:** *ROVE*, a creature-collecting survival game in Unreal Engine 5.8 with a full-roster rig and movement pipeline; *Glimmerfall* and *Hearthwild*, Godot 4 farming/creature RPGs; *Hoenn Openworld* and *Emerald Expedition*, Pokémon Emerald hacks with a Gen-9 open world, a one-way difficulty ladder and a procedural wilderness generator with an automated emulator test harness; *Reverie*, a simulated city for AI agents (~1,600 automated tests); [PocketDS](https://github.com/clark719664/PocketDS), an Android emulator front-end (private).
- **Live infrastructure:** dedicated multiplayer servers (Rust with custom C# Carbon plugins, Palworld, Don't Starve Together, Schedule I, All The Mods 10, Cobblemon) migrated to Linux with wipes, rosters and maintenance fully automated under systemd, a SYSTEM-level boot watchdog, and a homelab installed onto a display-less machine through WSL.
- **Mods:** a Cobblemon addon, a Schedule I gameplay mod (territory, spawns, in-game phone app), and NeoForge/Forge modpacks.
- **Tooling:** a local-LLM delegation toolkit with pre-tool hooks and a priced savings ledger, where every model earned its place through measured tests.

---

## How I work

1. **Measured, labelled, or removed.** A benchmark is reproducible or it is not cited. A simulation is called a simulation.
2. **Every fix ships with the test that would have caught it**, and a mutation check that the test actually fails without the fix.
3. **Standards are read, not remembered.** RFC 5766, RFC 9001 and the Lean kernel decide, not the comment above the code.
4. **PRs are small, stacked and explained**: what was wrong, what changed, what the tests prove, what is still unverified.

---

## Stack

<p>
<img alt="Rust" src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white">
<img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
<img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white">
<img alt="C#" src="https://img.shields.io/badge/C%23-512BD4?style=flat-square&logo=dotnet&logoColor=white">
<img alt="C++" src="https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&logo=cplusplus&logoColor=white">
<img alt="Java" src="https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white">
<img alt="Lean 4" src="https://img.shields.io/badge/Lean%204-6f42c1?style=flat-square">
<img alt="GDScript" src="https://img.shields.io/badge/GDScript-478CBF?style=flat-square&logo=godotengine&logoColor=white">
</p>
<p>
<img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white">
<img alt="Triton" src="https://img.shields.io/badge/Triton%20kernels-76B900?style=flat-square">
<img alt="CUDA" src="https://img.shields.io/badge/CUDA-76B900?style=flat-square&logo=nvidia&logoColor=white">
<img alt="QUIC" src="https://img.shields.io/badge/QUIC%20%2F%20STUN%20%2F%20TURN-0b5fff?style=flat-square">
<img alt="Soroban" src="https://img.shields.io/badge/Soroban%20SDK-7D00FF?style=flat-square&logo=stellar&logoColor=white">
<img alt="FastAPI" src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white">
<img alt="Tokio" src="https://img.shields.io/badge/Tokio-000000?style=flat-square">
</p>
<p>
<img alt="Unreal Engine" src="https://img.shields.io/badge/Unreal%20Engine%205-0E1128?style=flat-square&logo=unrealengine&logoColor=white">
<img alt="Godot" src="https://img.shields.io/badge/Godot%204-478CBF?style=flat-square&logo=godotengine&logoColor=white">
<img alt="Electron" src="https://img.shields.io/badge/Electron-47848F?style=flat-square&logo=electron&logoColor=white">
<img alt="Three.js" src="https://img.shields.io/badge/Three.js%20%2F%20WebGL-000000?style=flat-square&logo=threedotjs&logoColor=white">
<img alt="Linux" src="https://img.shields.io/badge/Linux%20%2F%20systemd-FCC624?style=flat-square&logo=linux&logoColor=black">
<img alt="Cloudflare" src="https://img.shields.io/badge/Cloudflare%20Workers-F38020?style=flat-square&logo=cloudflare&logoColor=white">
<img alt="PyInstaller" src="https://img.shields.io/badge/PyInstaller%20%2F%20NSIS-333333?style=flat-square">
</p>

---

<p align="center">
  <a href="https://github.com/clark719664"><img src="https://github-readme-stats.vercel.app/api?username=clark719664&show_icons=true&hide_border=true&theme=github_dark&include_all_commits=true&count_private=true" alt="GitHub stats" height="165"></a>
  <a href="https://github.com/clark719664"><img src="https://github-readme-stats.vercel.app/api/top-langs/?username=clark719664&layout=compact&hide_border=true&theme=github_dark&langs_count=8" alt="Top languages" height="165"></a>
</p>

<p align="center">Open to collaboration on distributed systems, protocol work, formal verification and game technology. Reach me through an issue or discussion on any repo above.</p>
