# Hi, I'm 0xNaezo

Solana Infrastructure Engineer focused on high-performance Rust backends. I build reliable, high-throughput network tools and asynchronous infrastructure for the Solana ecosystem

### Tech Stack
- **Core:** Rust (Tokio, Axum, SQLx, Tracing)
- **Web3:** Solana SDK, RPC/Helius integrations, Anchor
- **Data:** PostgreSQL (Job queues, indexing, relational design)


### Featured Project: CascadeRPC
**High-performance, protocol-agnostic JSON-RPC reverse proxy with tier-based spillover and sub-millisecond overhead.**

CascadeRPC acts as a bulletproof middleware layer between high-frequency applications (Web3 indexers, MEV bots, or heavy Web2 microservices) and upstream providers (e.g., Alchemy, Infura, Helius). It handles traffic spikes gracefully by enforcing provider-specific quotas, executing smart load-shedding, and seamlessly cascading excess requests to secondary infrastructure without dropping client connections.

*   **Lock-Free RCU Architecture (113k+ RPS):** Built on `Tokio` and `Axum`. Replaced heavy Mutex bottlenecks and Actor models with a Read-Copy-Update (RCU) pattern via `arc-swap`. This allows 100,000+ concurrent workers to read the routing table with zero blocking, achieving <1ms proxy overhead.
*   **Granular Rate Limiting & Smart Spillover:** Enforces hardware-level protection per upstream node. Combines `tokio::sync::Semaphore` (in-flight capping) and Token Bucket algorithms (`governor`). Instead of returning HTTP 429 bans under heavy load, it mathematically cascades traffic down priority tiers and uses an "earliest-available" wait strategy for micro-bursts.
*   **Zero-Copy Proxying & Deterministic Failover:** Avoids expensive full-payload JSON deserialization on the hot path by leveraging `bytes::Bytes`. It dynamically parses just enough to differentiate between non-retryable client errors (forwarded instantly) and network/limit failures (transparently retried via background health checks).

---

[Superteam Earn](-) | [X (Twitter)](https://x.com/0xNaezoDev) | [Telegram](https://t.me/x0Naezo)
