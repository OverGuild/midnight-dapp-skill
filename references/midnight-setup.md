# Midnight Development Setup

Prerequisites and setup steps for building on the Midnight Network.

## Prerequisites

-   **Node.js**: Version 18 LTS or higher.
-   **Git**: For version control.
-   **VS Code**: Recommended for Compact extension support.

## Toolchain Installation

### 1. Compact Compiler

Download the latest release of the Compact compiler from the [Midnight GitHub releases](https://github.com/midnight-ntwrk).

Add it to your PATH:
```bash
export PATH=$PATH:/path/to/compact/bin
```

### 2. VS Code Extension

Install the **Midnight Compact** extension for syntax highlighting and language support.

### 3. Wallet

Install the **Lace Wallet** (Midnight Devnet/Testnet version) to manage your test assets and sign transactions.

## Project Verification

To verify your setup, check the versions:

```bash
node --version
compact --version
```

## Faucet

Get test tokens from the [Midnight Testnet Faucet](https://faucet.midnight.network). You will need `tDUST` for transaction fees.
