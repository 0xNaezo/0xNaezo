# Hi, I'm 0xNaezo

Solana Infrastructure Engineer focused on high-performance Rust backends. 
I build reliable, asynchronous tools for on-chain data extraction and processing.

### Tech Stack
- **Core:** Rust (Tokio, Axum, SQLx, Tracing)
- **Web3:** Solana SDK, RPC/Helius integrations
- **Data:** PostgreSQL (Job queues, indexing, relational design)

### Featured Project: [AgentSafe](https://github.com/0xNaezo/AgentSafe) [🚧 Active Development]
**On-chain spending policy vaults for AI agents on Solana.** 
*(Encode Solana Bootcamp Capstone Project)*

AgentSafe solves the custody problem for AI agents. Instead of giving an AI full access to a wallet, AgentSafe provides a programmable on-chain vault. The agent can request payments, but the Solana program strictly enforces user-defined rules before moving any funds. 

*   **Smart Contract Core (Rust / Anchor):** PDA-based vaults enforcing daily spending limits, token mint locks, and recipient whitelists. The AI never holds custody.
*   **Solana Actions & Blinks:** Seamless "Manual Approval" flows. When an agent requests a payment outside its auto-limit, the vault owner receives a Blink in their X/Twitter feed to sign and approve the transaction.
*   **Full-Stack Integration:** Built with Next.js, a custom TypeScript SDK, and a reference AI intent parser translating natural language into strictly typed on-chain requests.

---

[Superteam Earn](-) | [X (Twitter)](https://x.com/0xNaezoDev) | [Telegram](https://t.me/x0Naezo)
