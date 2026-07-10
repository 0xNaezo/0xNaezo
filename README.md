# Hi, I'm 0xNaezo

Solana Infrastructure Engineer focused on high-performance Rust backends. I build reliable, high-throughput network tools and asynchronous infrastructure for the Solana ecosystem

### Tech Stack
- **Core:** Rust (Tokio, Axum, SQLx, Tracing)
- **Web3:** Solana SDK, RPC/Helius integrations, Anchor
- **Data:** PostgreSQL (Job queues, indexing, relational design)


### Featured Project: FluxRPC [🚧 Active Development]
**Adaptive Solana RPC load balancer with latency-aware routing and rate limit failover.**

FluxRPC acts as a protective middleware layer between high-frequency indexers/bots and Solana RPC providers (Helius, Alchemy, Public endpoints). It maximizes uptime and minimizes latency by intelligently routing requests, respecting provider-specific quotas, and seamlessly falling back to secondary nodes during degradation.

*   **Asynchronous High-Throughput Core:** Built on `Tokio` and `Axum`. Achieves extreme concurrency and minimal latency (sub-millisecond overhead) by replacing heavy Mutexes with lock-free atomic operations and Actor-model state management. 
*   **Granular Rate & Concurrency Limiting:** Enforces strict hardware-level protection per RPC node. Utilizes `tokio::sync::Semaphore` for in-flight request capping and GCRA (Token Bucket) algorithms to strictly respect individual RPS limits, completely preventing HTTP 429 bans.
*   **Zero-Copy Payload Propagation & Smart Failover:** Bypasses heavy JSON deserialization on the hot path using `bytes::Bytes` for zero-copy proxying. If a node returns a JSON-RPC error or timeouts, FluxRPC intercepts the failure and transparently retries on the next healthy node.


---

[Superteam Earn](-) | [X (Twitter)](https://x.com/0xNaezoDev) | [Telegram](https://t.me/x0Naezo)
