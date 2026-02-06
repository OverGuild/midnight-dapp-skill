<p align="center">
  <img src="assets/logo.png" alt="midnight-dapp-skill" width="200px">
</p>

<p align="center">
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square" alt="License: MIT"></a>
  <a href="https://midnight.network"><img src="https://img.shields.io/badge/Midnight-Network-1F2937.svg?style=flat-square" alt="Midnight Network"></a>
  <a href="https://docs.midnight.network"><img src="https://img.shields.io/badge/Compact-DSL-blue.svg?style=flat-square" alt="Compact"></a>
  <a href="https://www.typescriptlang.org/"><img src="https://img.shields.io/badge/TypeScript-Active-3178C6.svg?style=flat-square&logo=typescript" alt="TypeScript"></a>
</p>

<p align="center">
  <strong>A <a href="https://github.com/anthropics/skills">Claude Code skill</a> for building privacy-preserving dApps on Midnight Network.</strong>
  <br>
  <a href="https://docs.midnight.network">Midnight Docs</a> · <a href="#quick-start">Quick Start</a> · <a href="https://github.com/midnight-ntwrk">Midnight GitHub</a>
</p>

## What it does

This skill gives Claude Code deep knowledge of the Midnight development stack so it can help you:

- **Scaffold** Midnight dApps with Compact contracts and TypeScript frontends
- **Write** ZK-powered smart contracts using the Compact language
- **Compile** circuits and generate TypeScript interfaces
- **Interact** with the Midnight ledger using the JS SDK
- **Manage** private and public state effectively

## Quick Start

```bash
bash <(curl -s https://raw.githubusercontent.com/OverGuild/midnight-dapp-skill/main/install.sh)
```

Then start Claude Code and ask it to build something:

```
> Create a Midnight contract for a confidential voting system
```

## Stack

| Layer | Tool | Notes |
|:------|:-----|:------|
| Smart Contracts | **Compact** | ZK-circuit based contract language |
| Client SDK | **Midnight JS** | `@midnight-ntwrk/midnight-js-contracts` |
| Wallet | **Lace** | Managing assets and signing transactions |
| Runtime | **Node.js 18+** | Required environment |

<details>
<summary><strong>Prerequisites</strong></summary>

<br>

- [Node.js](https://nodejs.org/) 18+
- [Git](https://git-scm.com/)
- [Lace Wallet](https://www.lace.io/) (Midnight compatible version)
- VS Code (Recommended)

</details>

## Usage examples

Once installed, start a Claude Code session and try:

```
> Help me start a new Midnight dApp
> Write a Compact contract for a private token
> Explain how private state works in Midnight
> Create a script to deploy my contract
```

## Skill structure

```
midnight-dapp-skill/
├── SKILL.md                            # Main skill definition
├── references/
│   ├── midnight-compact.md             # Compact language guide
│   ├── midnight-js-client.md           # JS SDK guide
│   └── midnight-setup.md               # Setup guide
├── install.sh
├── assets/
│   └── logo.png
└── README.md
```

## Resources

| Resource | Description |
|:---------|:------------|
| [Midnight Docs](https://docs.midnight.network) | Official documentation |
| [Midnight Academy](https://academy.midnight.network) | Learning resources |
| [Midnight GitHub](https://github.com/midnight-ntwrk) | Open source tools/libs |

## License

[MIT](LICENSE)
