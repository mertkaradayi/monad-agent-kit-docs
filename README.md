# Monad Agent Kit

TypeScript SDK for building AI agents that interact with Monad blockchain.

**[Read the Documentation](https://mertkaradayi.github.io/monad-agent-kit-docs/)**

## Packages

| Package | Description |
|---------|-------------|
| [`@monad-agent-kit/core`](https://www.npmjs.com/package/@monad-agent-kit/core) | Core SDK — agent, plugin system, wallet management |
| [`@monad-agent-kit/plugin-token`](https://www.npmjs.com/package/@monad-agent-kit/plugin-token) | ERC-20 and native MON token operations |
| [`@monad-agent-kit/plugin-tokens`](https://www.npmjs.com/package/@monad-agent-kit/plugin-tokens) | Token info, pricing, portfolio, discovery |
| [`@monad-agent-kit/plugin-nft`](https://www.npmjs.com/package/@monad-agent-kit/plugin-nft) | ERC-721 NFT query, transfer, metadata |
| [`@monad-agent-kit/plugin-defi`](https://www.npmjs.com/package/@monad-agent-kit/plugin-defi) | DEX swaps, liquidity, staking via Kuru & 0x |
| [`@monad-agent-kit/ai-vercel`](https://www.npmjs.com/package/@monad-agent-kit/ai-vercel) | Vercel AI SDK integration |
| [`@monad-agent-kit/ai-langchain`](https://www.npmjs.com/package/@monad-agent-kit/ai-langchain) | LangChain integration |

## Quick Start

```bash
bun add @monad-agent-kit/core @monad-agent-kit/plugin-token @monad-agent-kit/plugin-defi
```

```typescript
import { MonadAgentKit } from "@monad-agent-kit/core"
import { tokenPlugin } from "@monad-agent-kit/plugin-token"
import { defiPlugin } from "@monad-agent-kit/plugin-defi"

const agent = new MonadAgentKit({
  privateKey: process.env.PRIVATE_KEY,
  chainId: 10143, // Monad Testnet
})

await agent.use(tokenPlugin)
await agent.use(defiPlugin)

const balance = await agent.execute("getBalance", {})
console.log(`Balance: ${balance.data.balance} MON`)
```

## Features

- **Plugin Architecture** — Modular design with token, DeFi, NFT, and custom plugins
- **40+ Actions** — Transfers, swaps, liquidity, staking, NFTs, portfolio tracking
- **AI Framework Support** — Vercel AI SDK, LangChain, Claude Desktop (MCP)
- **Type-Safe** — Full TypeScript with comprehensive types
- **Name Resolution** — Built-in ENS (.eth) and MNS (.mon) support

## License

MIT
