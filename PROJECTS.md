# Public project catalog

[Back to profile](https://github.com/clark719664)

All **14 public repositories** under [clark719664](https://github.com/clark719664?tab=repositories), verified **24 October 2026**. This is a catalog of public work, not an inventory of private or local projects. Screenshots are existing project captures, not new measurements.

## Released apps and browser demos

### PC Cast & TV apps

**Original app family · desktop releases; mobile beta**  
[Repository](https://github.com/clark719664/pc-tv-apps) · [Website](https://clark719664.github.io/pc-tv-apps/) · [Releases](https://github.com/clark719664/pc-tv-apps/releases)

Four desktop editions bring casting and TV controls together: PC Cast Pro combines a video library, casting, remote control, multi-screen grids, and live TV; PC Cast Lite focuses on casting; PC TV Live provides a channel guide; PC TV Remote provides TV controls.

- **Delivery:** Windows installers and Linux archives, release notes, checksums, and bundled-tool source. [PC Cast Pro Windows 2026.10.23.1](https://github.com/clark719664/pc-tv-apps/releases/tag/v2026.10.23.1) is a specific edition update, not a simultaneous update of all editions.
- **Mobile:** standalone Android Live/Remote betas and a [mobile Live web app](https://clark719664.github.io/pc-tv-apps/live/). [TV Remote beta3](https://github.com/clark719664/pc-tv-apps/releases/tag/mobile-v2026.10.24-beta3) supersedes the old Remote beta1 link. Consult the repository's download matrix for each app's current build.
- **Limits:** mobile editions have fewer features than Pro/Lite. TV compatibility varies; the documented testing is on the developer's own network. Public releases do not establish compatibility with every TV.

### Lucent

**Original browser app · live demo**  
[Repository](https://github.com/clark719664/lucent) · [Try Lucent](https://clark719664.github.io/lucent/)

A progressive TypeScript/WebGL2 path tracer with a custom glTF parser, BVH builder, and integrator. It supports PBR textures, clearcoat, sheen, refractive glass, HDR environment sampling, denoising, and temporal reprojection.

- **Evidence:** the repository's [gallery](https://github.com/clark719664/lucent#gallery), source, and CI workflow; the profile reuses its Car Concept render.
- **Engineering focus:** rendering quality within a selectable GPU budget, including presets and a GPU timing-based recommendation.
- **Limits:** requires WebGL2; performance and convergence depend on the device, scene, and settings. No universal frame-rate claim is made here.
- **Credits:** Car Concept by Darmstadt Graphics Group, CC BY. Model and HDRI attribution is retained in the [project credits](https://github.com/clark719664/lucent#credits).

### Synapse

**Original browser app · live demo**  
[Repository](https://github.com/clark719664/synapse) · [Try Synapse](https://clark719664.github.io/synapse/)

A TypeScript/WebGL2 trace explorer that turns spans into a service map and waterfalls. It imports OTLP/JSON, Jaeger, and Zipkin data and includes a reproducible simulator. Live mode visualizes Wikimedia EventStreams, with a globe showing edited pages that have coordinates—not editor locations.

- **Evidence:** public source, gallery, parser tests, and collector tests documented in the repository.
- **Architecture:** the live stream connects directly from the browser. A separate Python collector publishes rolling history; that history feature has an external dependency even though the explorer runs in the browser.
- **Limits:** Wikimedia availability, replay coverage, and collector freshness affect live history. The simulator is synthetic; it is not production telemetry. This is not a complete hosted APM service or a browser OTLP/gRPC receiver.

## Research and engineering experiments

### Godot Rollback Coherence

**Original integration and regression harness · bounded fixture**  
[Repository](https://github.com/clark719664/godot-rollback-coherence) · [Recorded CI run](https://github.com/clark719664/godot-rollback-coherence/actions/runs/40045303203) · [Upstream issue](https://github.com/appsinacup/godot-rapier-physics/issues/534)

Repairs collision-query scheduling and dictionary-order hashing in a Godot/Rapier bomb-game fixture. Two real headless peers exchange ENet traffic through a delayed loopback path; confirmed states are compared with a zero-delay reference. Regression controls deliberately restore the faulty ordering.

**Scope:** the fixture's registered StaticBody2D hitboxes, pinned binaries, and tested local Windows setup. This does not establish general cross-platform determinism, arbitrary dynamic-body restoration, or Area signal replay. The harness preserves the distinction between successful snapshot calls and verified physical restores. Original fixture binaries are fetched from upstream rather than redistributed.

### Ruffle Portable States

**Original experimental patch and fixture · sealed AVM1 subset**  
[Repository](https://github.com/clark719664/ruffle-portable-states) · [Recorded CI run](https://github.com/clark719664/ruffle-portable-states/actions/runs/40045730753)

Checkpoints a running SWF, exits the producer, and restores into a fresh Ruffle player without replaying earlier frames. The original collect-square fixture exercises keyboard input, RNG, display state, and deterministic continuation.

**Evidence:** the repository records 17 selected passing tests, subprocess restore helpers, a pinned upstream base, and an independent review. That is the selected suite, not all Ruffle tests. **Scope:** a validated sealed AVM1 movie contract; arbitrary Flash games, general functions/objects, audio/video, timers, loaders, and external callbacks remain unsupported.

### Adobe Tone Lab

**Original measurement kit · negative research result**  
[Repository](https://github.com/clark719664/adobe-tone-lab) · [Preview study](https://github.com/clark719664/adobe-tone-lab/blob/main/PREVIEW.md) · [Native-stage appendix](https://github.com/clark719664/adobe-tone-lab/blob/main/linear_research/README.md) · [Recorded CI run](https://github.com/clark719664/adobe-tone-lab/actions/runs/40047325928)

Preserves 126 real Adobe DNG Converter previews plus 14 texture-control previews in the native-stage appendix, with provenance checks and reproducible experiments. The main benchmark predicts edited 8-bit sRGB previews from Adobe default previews.

**Result:** no improved operator passed the generalization gate. Adobe-equivalent rendering remains unsolved. Research-visible validation families were reused; future selection needs untouched families and photographic data. Conditional postrender prediction is not RAW-stage equivalence. The separate 16-bit TIFF fidelity path remains unfinished, and diagnostic counterfactuals are not deployable predictors.

## Open-source contribution forks

These repositories are forks of other maintainers' projects. Contribution status below refers to linked upstream pull requests, not ownership of the upstream product. Status checked 1 November 2026.

### HiveMind

**Contribution fork · merged upstream work**  
[Clark's fork](https://github.com/clark719664/HiveMind) · [Upstream](https://github.com/xaviercallens/HiveMind) · [Merged PRs by Clark](https://github.com/xaviercallens/HiveMind/pulls?q=is%3Apr+author%3Aclark719664+is%3Amerged)

Contributions span networking, GPU kernels, routing/compression, serving, and Lean 4 models:

- **Networking:** [QUIC 0-RTT and STUN/TURN implementation with loopback tests (#40)](https://github.com/xaviercallens/HiveMind/pull/40), and [TURN ChannelBind protocol correction (#73)](https://github.com/xaviercallens/HiveMind/pull/73).
- **GPU work:** [INT4/FP8 fused router work (#23)](https://github.com/xaviercallens/HiveMind/pull/23) and [CUDA-stream expert prefetching (#7)](https://github.com/xaviercallens/HiveMind/pull/7).
- **Compression and models:** [error-feedback implementation (#63)](https://github.com/xaviercallens/HiveMind/pull/63), [worker-path integration (#69)](https://github.com/xaviercallens/HiveMind/pull/69), and [Lean conservation/bounds work (#68)](https://github.com/xaviercallens/HiveMind/pull/68).
- **Evidence quality:** [CI collection repair (#67)](https://github.com/xaviercallens/HiveMind/pull/67) and [benchmark/reporting corrections (#77)](https://github.com/xaviercallens/HiveMind/pull/77).

**Limits:** synthetic compression/routing benchmarks do not establish trained-model quality or production speedups. GPU kernel code and tests do not by themselves establish validated hardware performance. Lean theorems cover their formal models and assumptions, not every property of the deployed Python/CUDA system. No unvalidated 7B benchmark is used as portfolio evidence.

### Other contribution forks

**[Protocol-Canary](https://github.com/clark719664/Protocol-Canary)** — `getHealth` RPC compatibility support; [StellarCanary #570](https://github.com/StellarCanary/Protocol-Canary/pull/570), **merged**.

**[Credence-Contracts](https://github.com/clark719664/Credence-Contracts)** — Rust/Soroban bounty-escrow entry points and paginated views; [CredenceOrg #1636](https://github.com/CredenceOrg/Credence-Contracts/pull/1636), **merged**.

**[FancyModLoader](https://github.com/clark719664/FancyModLoader)** — DebugFile appender fix for unavailable Netty native transport; [NeoForged #468](https://github.com/neoforged/FancyModLoader/pull/468), **closed without review** (the maintainers closed all external PRs in a sweep on 31 October 2026).

**[StellarGrantProtocol](https://github.com/clark719664/StellarGrantProtocol)** — Active-grant check in `swap_and_pay` ([#1350](https://github.com/PhasoraLabs/StellarGrantProtocol/pull/1350)) and rejection of quorum-failed proposals ([#1351](https://github.com/PhasoraLabs/StellarGrantProtocol/pull/1351)); both **closed without merge**.

The dated audit found **48 merged upstream PRs** across the listed contribution work: 46 HiveMind + Protocol-Canary #570 + Credence #1636. Open and closed-unmerged submissions are excluded. Counts change; the linked PR records are the evidence.

### Open pull requests (1 November 2026)

- **[excalidraw](https://github.com/clark719664/excalidraw)** — arrow-type switching for bound and labeled arrows ([#12503](https://github.com/excalidraw/excalidraw/pull/12503)), stable canvas search results while editing ([#12504](https://github.com/excalidraw/excalidraw/pull/12504)), searchable shortcuts in the help dialog ([#12505](https://github.com/excalidraw/excalidraw/pull/12505)); all **open**.
- **[highlight.js](https://github.com/clark719664/highlight.js)** — PHP one-line comments end at the closing `?>` ([#4572](https://github.com/highlightjs/highlight.js/pull/4572)); Ruby `Name::method` is a scope resolution, not a symbol ([#4573](https://github.com/highlightjs/highlight.js/pull/4573)); both **open**.
- **[mermaid](https://github.com/clark719664/mermaid)** — esbuild plugin that strips chevrotain's unreachable `eval` from the minified bundles, removing a Firefox console warning ([#8649](https://github.com/mermaid-js/mermaid/pull/8649)); **open**.
- **[vitest](https://github.com/clark719664/vitest)** and **[nuxt](https://github.com/clark719664/nuxt)** — verified fixes for seeded file-shuffle order (vitest #11340), watch mode after a config restart (vitest #11772) and the 100 ms navigation delay under view transitions (nuxt #36768) live on fork branches; the two submitted PRs were closed by an automated account check, not on technical review.

## Reference forks

- **[lumina-backend](https://github.com/clark719664/lumina-backend)** — reference fork of [Lumeeena/lumina-backend](https://github.com/Lumeeena/lumina-backend), a Stellar indexer and GraphQL API. No authored upstream contribution is claimed here.
- **[lumentix](https://github.com/clark719664/lumentix)** — reference fork of [LumenTix-HQ/lumentix](https://github.com/LumenTix-HQ/lumentix). No authored upstream contribution is claimed here.

## Profile repository

- **[clark719664](https://github.com/clark719664/clark719664)** — this profile and its public-project catalog.

Private and unreleased work is excluded from this public evidence catalog. The previous profile mentioned additional games, infrastructure, mods, and tools; those descriptions need a separate current review before being promoted as case studies.
