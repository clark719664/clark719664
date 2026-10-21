### Hi, I'm Clark 👋

**Systems engineer: Rust, Stellar/Soroban, distributed ML infrastructure and Lean 4 formal verification.** I ship working code with tests, and I don't let a claim stand that the code can't back up.

**16 merged upstream PRs** · **Lean 4 proofs merged upstream** · **4 shipped apps for Windows and Linux**

---

#### 🧠 Distributed ML infrastructure: [xaviercallens/HiveMind](https://github.com/xaviercallens/HiveMind)

Decentralized LoRA training over a QUIC "Geo-Ring". 15 of my PRs are merged there, and I have write access to the repo.

- **Transport:** async QUIC with 0-RTT resumption and WebSocket fallback ([#9](https://github.com/xaviercallens/HiveMind/pull/9)), multi-node WAN NAT traversal with STUN/TURN and UDP hole punching ([#22](https://github.com/xaviercallens/HiveMind/pull/22)), then a real QUIC 0-RTT and STUN/TURN implementation ([#40](https://github.com/xaviercallens/HiveMind/pull/40)).
- **GPU kernels:** Triton `float8_e4m3fn` kernel and causal tree-attention mask ([#8](https://github.com/xaviercallens/HiveMind/pull/8)), INT4 + FP8 fused MoE router kernel with a benchmark ([#23](https://github.com/xaviercallens/HiveMind/pull/23)), double-buffered CUDA stream prefetcher ([#7](https://github.com/xaviercallens/HiveMind/pull/7)).
- **Serving and models:** SSE streaming for `/v1/chat/completions` ([#6](https://github.com/xaviercallens/HiveMind/pull/6)), domain-expert LoRA adapters with a Top-k FP8 content-addressed registry ([#25](https://github.com/xaviercallens/HiveMind/pull/25)).
- **In review:** an error-feedback residual for Top-k + FP8 compression ([#63](https://github.com/xaviercallens/HiveMind/pull/63)), wired into the real worker upload path ([#69](https://github.com/xaviercallens/HiveMind/pull/69)).

#### 📐 Formal verification (Lean 4)

- Proved prefix-trie speculative acceptance and RFC 9001 0-RTT bounds ([#21](https://github.com/xaviercallens/HiveMind/pull/21)).
- Reworked theorems so they prove properties of the **actual** protocols, not restatements of their assumptions ([#41](https://github.com/xaviercallens/HiveMind/pull/41), [#39](https://github.com/xaviercallens/HiveMind/pull/39)). The pipeline no longer reports an unchecked proof as verified.
- In review: the error-feedback update modeled in Lean, with conservation (including decay and clipping) and the Top-k contraction rate proved ([#68](https://github.com/xaviercallens/HiveMind/pull/68)).

#### ⭐ Stellar & Soroban

- **[StellarCanary/Protocol-Canary](https://github.com/StellarCanary/Protocol-Canary):** `getHealth` support in the RPC compatibility checker ([#570](https://github.com/StellarCanary/Protocol-Canary/pull/570), merged).
- **[CredenceOrg/Credence-Contracts](https://github.com/CredenceOrg/Credence-Contracts):** bounty-escrow contract entry points and paginated views ([#1636](https://github.com/CredenceOrg/Credence-Contracts/pull/1636), in review).

#### 🔍 Rigor is the feature

I fix the gap between what a project claims and what its code does: an astrophysics demo that reported speedups it never measured ([#65](https://github.com/xaviercallens/HiveMind/pull/65)), synthetic results labelled as real ([#64](https://github.com/xaviercallens/HiveMind/pull/64)), and an import cycle that silently stopped CI on `main` ([#67](https://github.com/xaviercallens/HiveMind/pull/67)).

---

#### 📺 Shipped products: IN3RT1A apps for Windows and Linux

Free apps that get your PC and your TVs working together, published at **[payhip.com/IN3RT1A](https://payhip.com/IN3RT1A)** with installers and Linux builds on **[pc-tv-apps](https://github.com/clark719664/pc-tv-apps)**:

- **PC Cast Pro:** a TV remote, casting from any link or embedded player, multicast to many TVs at once, your PC's video library, multi-screen grids and free live TV, all in one app.
- **PC Cast Lite:** casting only. **PC TV Live:** free live TV by country with a guide, built on a documented legal-source filter. **PC TV Remote:** the remote only.

Each one is a one-click Windows installer that needs no administrator rights and bundles what it needs (and a Linux tarball with a one-command install and optional systemd service), with SHA-256 checksums and the corresponding source for bundled GPL tools published on every release. Tested by me on TVs on my own network. See the [screenshots and downloads](https://github.com/clark719664/pc-tv-apps#screenshots).

They're free with no ads. If they're useful to you, **[a donation from $1](https://payhip.com/b/Wn9fE)** keeps them that way, and an approved donor message scrolls on every app's home screen ([how it works](https://github.com/clark719664/pc-tv-apps#keep-it-free)).

---

#### 🛠️ Stack

`Rust` · `Soroban SDK` · `Stellar XDR` · `Python` · `PyTorch` · `Triton` · `CUDA` · `Lean 4` · `Tokio` · `QUIC` · `TypeScript` · `PyInstaller` · `NSIS`
