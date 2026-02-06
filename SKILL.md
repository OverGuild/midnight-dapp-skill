---
name: midnight-dapp-skill
description: Guide for building privacy-preserving dApps on Midnight Network using Compact and TypeScript. Covers contract development, ZK proofs, and frontend integration. Use when starting a new Midnight project, writing Compact contracts, or building a frontend that interacts with the Midnight ledger.
---

# Midnight dApp Development

## Stack

| Layer | Tool | Notes |
|-------|------|-------|
| Smart Contracts | **Compact** DSL | Writes ZK circuits and ledger logic. Compiles to WASM/ZKIR. |
| Client SDK | **Midnight JS** / **MeshJS** | TypeScript SDKs for interacting with contracts and wallets. |
| Wallet | **Lace** | Primary wallet for Midnight Network assets. |
| Local Toolchain | `compact` CLI | Compiler for Compact contracts. |
| Runtime | Node.js 18+ | Required for the JS client and toolchain. |

## Decision Flow

When starting a new Midnight project:

1.  **Define Privacy Needs**: Identify which data must remain private (ZK inputs) and what goes on the public ledger.
2.  **Write Contract**: Use **Compact** (`.compact` files) to implement the logic.
3.  **Compile**: Use `compact compile` to generate TypeScript wrappers.
4.  **Build Frontend**: Import the generated wrappers into your React/Next.js app.

## Project Scaffolding

### Recommended Structure

```
my-midnight-dapp/
├── contracts/
│   └── token.compact          # Compact contract logic
├── src/
│   ├── managed/               # Auto-generated TS wrappers
│   └── components/            # Frontend components
├── tests/                     # Contract tests
├── midnight.config.ts         # Network config
└── package.json
```

### Bootstrap steps

```bash
# 1. Initialize project
mkdir my-midnight-dapp && cd my-midnight-dapp
npm init -y

# 2. Install dependencies
npm install @midnight-ntwrk/midnight-js-contracts @meshsdk/midnight-setup

# 3. Create contract
mkdir contracts
touch contracts/counter.compact
```

## Core Workflow

### 1. Write Contract (Compact)

```typescript
// contracts/counter.compact
contract Counter {
    ledger field value: Uint<32>;

    constructor() {
        value = 0;
    }

    circuit increment(): void {
        value = value + 1;
    }
}
```

### 2. Compile

```bash
compact compile contracts/counter.compact src/managed/counter
```

### 3. Deploy & Interact (TypeScript)

```typescript
import { deployContract } from './managed/counter.js';
import { getWallet } from '@meshsdk/midnight-setup';

const wallet = await getWallet();
const deployment = await deployContract(wallet, ...);
const contract = await deployment.getContract(wallet);

await contract.callTx.increment();
```

## Principles

-   **Privacy First**: Always design your data model around what *needs* to be public vs. private.
-   **Type Safety**: Rely on the generated TypeScript wrappers in `src/managed/` to prevent runtime errors.
-   **User Control**: Remember that private state is managed client-side (in the user's wallet/browser).

## References

-   `references/midnight-compact.md` — Guide to Compact language.
-   `references/midnight-js-client.md` — Using the JS SDK.
-   `references/midnight-setup.md` — Environment setup.
