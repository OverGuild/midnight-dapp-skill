# Midnight JS Client

The Midnight JS Client (`@midnight-ntwrk/midnight-js-contracts`) is the primary way to interact with Midnight smart contracts from a frontend or Node.js application.

## Installation

```bash
npm install @midnight-ntwrk/midnight-js-contracts @meshsdk/midnight-setup
```

## Core Components

-   **Wallet Provider**: Connects to Lace or other Midnight-compatible wallets.
-   **Contract API**: Generated from your Compact contract.
-   **Providers**: RPC providers for submitting transactions.

## Basic Usage

### 1. Connect Wallet

```typescript
import { getWallet } from '@meshsdk/midnight-setup';

const wallet = await getWallet();
```

### 2. Deploy Contract

```typescript
import { deployContract } from './managed/my_contract.js'; // Generated wrapper

const deployment = await deployContract(wallet, {
  privateStateKey: 'initial_value',
});

console.log('Contract Address:', deployment.deployTxData.public.contractAddress);
```

### 3. Interact with Contract

```typescript
const contract = await deployment.getContract(wallet);

const tx = await contract.callTx.myFunction(arg1, arg2);
console.log('Transaction ID:', tx.txId);
```

## Best Practices

-   **Type Safety**: Always use the generated TypeScript wrappers in `src/managed/`.
-   **Error Handling**: Handle ZK proof generation delays and network timeouts gracefully.
-   **State Management**: Carefully manage local private state synchronization.
