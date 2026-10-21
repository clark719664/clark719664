### Hi, I'm Clark 👋

**Systems engineer: Rust, Stellar/Soroban, distributed ML infrastructure and Lean 4 formal verification.** I ship working code with tests, and I don't let a claim stand that the code can't back up.

**16 merged upstream PRs** · **Lean 4 proofs merged upstream** · **3 shipped Windows apps**

---

#### 🧠 Distributed ML infrastructure: [xaviercallens/HiveMind](https://github.com/xaviercallens/HiveMind)

Decentralized LoRA training over a QUIC "Geo-Ring". 15 of my PRs are merged there, and I co-own several of its subsystems.

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

#### 📺 Shipped products: IN3RT1A apps for Windows

Free apps that get your PC and your TVs working together, published at **[payhip.com/IN3RT1A](https://payhip.com/IN3RT1A)** with installers on **[pc-tv-apps](https://github.com/clark719664/pc-tv-apps)**:

- **PC Cast Pro:** a TV remote, casting from any link, your PC's video library, multi-screen grids and live TV, all in one app.
- **PC Cast Lite:** casting only. **PC TV Remote:** the remote only.

Each one ships as an offline one-click installer with everything included (frozen Python, Chromium, FFmpeg/FFprobe, ADB), with signed-package provenance and a GPL source pack. Every installer is tested by installing, running, uninstalling and reinstalling it on Windows before release.

---

#### 🛠️ Stack

`Rust` · `Soroban SDK` · `Stellar XDR` · `Python` · `PyTorch` · `Triton` · `CUDA` · `Lean 4` · `Tokio` · `QUIC` · `TypeScript` · `PyInstaller` · `NSIS`
