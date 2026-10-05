# Nova Shield Chain

A Layer 1 blockchain I've been building in Rust for the past year. Solo. No team, no VC backing.

Testnet is live as of October 2026. Three validators running in Docker, blocks producing every 400ms, BFT consensus holding.

---

## Why I built this

Every DEX trade you make is visible before it executes. MEV bots are reading your mempool, front-running you, and there's nothing you can do about it on existing chains — because privacy wasn't part of the design, it was bolted on later.

Nova Shield Chain is built privacy-first from genesis. ZK shielded transactions are a core primitive, not a plugin.

---

## What's under the hood

- **Consensus:** BFT, 400ms block time, 2/3 quorum
- **ZK:** Real Groth16 proofs on BLS12-381 (arkworks). Not mock proofs — actual circuits for Mint, Transfer, Burn, Spend.
- **Signatures:** BLS aggregate + sr25519 VRF for leader election
- **P2P:** Noise XX handshake (X25519 + ChaCha20-Poly1305)
- **Storage:** RocksDB
- **RPC:** JSON-RPC over HTTP

20 crates, 100k+ lines of Rust, 3260+ tests passing. Security audit suite is built into the repo with property-based tests on every module.

---

## Codebase structure

```
nova-consensus/     BFT engine, VRF
nova-crypto/        BLS, KZG, Noise XX
nova-zk/            Groth16 circuits
nova-network/       TCP transport, peer discovery
nova-runtime/       Transaction pipeline, state
nova-rpc/           JSON-RPC (axum)
nova-node/          Full node, genesis, orchestration
nova-vm/            Execution engine
nova-mempool/       Tx pool
nova-sdk/           Client SDK
+ 10 more
```

---

## Token

$NSC — 200M fixed supply, deflationary (50% fee burn). Chain ID 42000.

---

## Status

Testnet running. Mainnet prep in progress.

Source is closed during pre-mainnet phase. Audit results and verified builds available on request.

---

**X:** [@NovaShieldChain](https://x.com/NovaShieldChain)
