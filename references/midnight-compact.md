# Midnight Compact Contracts

Compact is a domain-specific language (DSL) for writing smart contracts on the Midnight Network. It is designed to handle ZK-proof generation and private state transitions.

## Key Concepts

-   **Circuit Logic**: Compact compiles to ZK circuits that verify computations.
-   **Private State**: Data can be kept private to the user, with only proofs submitted to the chain.
-   **Public State**: Shared state on the ledger (like standard smart contract state).

## Contract Structure

A standard Compact project structure:

```
my-midnight-dapp/
├── contracts/
│   └── my_contract.compact    # The smart contract logic
├── src/
│   ├── managed/               # Auto-generated TypeScript types
│   └── index.ts               # Application logic
├── midnight.config.ts         # Network configuration
└── tests/                     # Contract tests
```

## Compilation

Use the Compact compiler to generate the TypeScript interfaces and ZK artifacts:

```bash
compact compile contracts/my_contract.compact src/managed/my_contract
```

## Example Workflow

1.  **Define Contract**: Write your logic in `.compact`.
2.  **Compile**: Generate the standard circuit and TS wrappers.
3.  **Deploy**: Use the Midnight JS SDK to deploy the contract.
4.  **Interact**: Call contract methods via the generated TypeScript API.

## Resources

-   [Official Compact Documentation](https://docs.midnight.network)
-   [Midnight Academy](https://academy.midnight.network)
