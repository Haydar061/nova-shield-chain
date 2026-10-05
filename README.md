# Nova Shield Chain ⚡

> **Layer 1 blockchain built in Rust. Privacy-first DeFi. Testnet live.**

[![Testnet](https://img.shields.io/badge/Testnet-Live-brightgreen)](https://github.com/Haydar061/nova-shield-chain)
[![Language](https://img.shields.io/badge/Language-Rust-orange)](https://www.rust-lang.org/)
[![Consensus](https://img.shields.io/badge/Consensus-BFT-blue)](https://github.com/Haydar061/nova-shield-chain)
[![ZK](https://img.shields.io/badge/ZK-Groth16%20BLS12--381-purple)](https://github.com/Haydar061/nova-shield-chain)

---

## What is Nova Shield Chain?

Nova Shield Chain is an independent Layer 1 blockchain built from scratch in Rust, designed for **privacy-first DeFi** — where your trading strategy stays yours, not MEV bots'.

Built by a solo developer. No VC funding. No shortcuts.

---

## Core Features

| Feature | Implementation |
|---|---|
| Consensus | BFT (400ms block time) |
| ZK Proofs | Groth16 — BLS12-381 (arkworks) |
| Signatures | BLS aggregate signatures |
| VRF | sr25519 schnorrkel ristretto255 |
| Polynomial Commitments | KZG — BLS12-381 |
| P2P Encryption | Noise XX (X25519 + ChaCha20-Poly1305) |
| Storage | RocksDB persistent |
| RPC | JSON-RPC over HTTP (axum) |
| Privacy | ZK shielded transactions (Mint/Transfer/Burn/Spend) |

---

## Testnet Status 🔴 Live

- **3 validators** running in Docker
- **400ms** block time
- **BFT consensus** with 2/3 quorum
- Validators in sync, RPC responding

---

## Technical Highlights

- **100,000+ lines of Rust** across 20 crates
- **3,260+ tests** — zero failures
- **Security audit suite** built-in (13 modules + property-based testing)
- **Real ZK circuits** — not mock proofs (MintCircuit, TransferCircuit, BurnCircuit, SpendCircuit)
- **Production-grade** error handling throughout

---

## Architecture

```
nova-shield-chain/
├── nova-consensus     # BFT engine, VRF leader election
├── nova-crypto        # BLS, ZK, KZG, Noise XX
├── nova-zk            # Groth16 circuits (Mint/Transfer/Burn/Spend)
├── nova-network       # TCP async transport, peer discovery
├── nova-runtime       # Transaction pipeline, state machine
├── nova-rpc           # JSON-RPC server (axum)
├── nova-node          # Full node, genesis, services
├── nova-vm            # Smart contract execution
├── nova-mempool       # Transaction pool
├── nova-sdk           # Client SDK
└── ... (20 crates total)
```

---

## Why Nova Shield Chain?

Current DEX trading is broken:
- MEV bots front-run your transactions
- Your strategy is public before execution
- Privacy is an afterthought, not a foundation

Nova Shield Chain solves this at the protocol level with **native ZK shielded transactions** — privacy built-in from genesis, not bolted on.

---

## Token

**$NSC — Nova Shield Chain**
- Fixed supply: 200,000,000 NSC
- Deflationary: 50% fee burn
- Chain ID: 42000

---

## Code

The codebase is currently **closed source** during the pre-mainnet phase.

Verified builds and audit results available upon request.

---

## Contact

- Twitter/X: [@NovaShieldChain](https://x.com/NovaShieldChain)
- Email: coming soon

---

*Built with stubbornness and Rust.*
