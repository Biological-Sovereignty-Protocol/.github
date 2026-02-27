# Contributing to the Biological Sovereignty Protocol (BSP)

First off, thank you for considering contributing to the Biological Sovereignty Protocol! It's people like you who make this decentralized ecosystem a reality, ensuring human biological data remains sovereign, secure, and permanent.

## 🧬 Our Philosophy

The Biological Sovereignty Protocol is built on the belief that **individuals must have absolute cryptographic ownership of their clinical and biological history.** We build on Arweave (permanent storage) and SmartWeave (decentralized computation) to guarantee this.

Whether you are fixing a typo in the documentation, building a new SDK feature, or proposing an entirely new Institutional Intent standard, your contributions matter.

## 🏗️ The Ecosystem Architecture

Before diving in, please familiarize yourself with the core pillars of the BSP ecosystem:

1. **[bsp-registry](https://github.com/Ambrosio-Institute/bsp-registry)**: The immutable SmartWeave contracts (BEORegistry, IEORegistry, AccessControl) stewarded by the Ambrosio Institute.
2. **[@bsp/sdk](https://github.com/Biological-Sovereignty-Protocol/bsp-sdk-typescript)**: The TypeScript standard library for interacting with the contracts.
3. **[bsp-registry-api](https://github.com/Ambrosio-Institute/bsp-registry-api)**: The protocol relayer for gas abstraction and off-chain Guardian notifications.
4. **[bsp-mcp](https://github.com/Biological-Sovereignty-Protocol/bsp-mcp)**: The Model Context Protocol integration bridging AI with sovereign biological data.

## 🤝 How to Contribute

### 1. Proposing a Change (Issues)
If you have an idea for a massive feature or a structural change to the SmartWeave contracts, please **open an issue first**. 
For the core contracts (`bsp-registry`), structural changes usually require a formal Proposal to the on-chain Governance contract. Discussing it in an issue first saves everyone time.

### 2. Submitting Pull Requests
1. **Fork** the repository you want to contribute to.
2. **Clone** your fork locally.
3. Create a feature branch (`git checkout -b feat/add-new-intent`).
4. Commit your changes. Ensure your commit messages are descriptive.
5. Push your branch and open a Pull Request against the `main` branch.

### 3. Development Guidelines
* **TypeScript:** We use strict TypeScript across the board (SDK, API, MCP). Ensure `npm run build` and `npm run lint` pass.
* **SmartWeave Contracts:** Contracts are written in vanilla JavaScript (ES2020) for Warp compatibility. Tests must use `warp-contracts-testing`.
* **Tests:** If you add a feature, add a test. If you fix a bug, add a test that prevents the bug from recurring.

## 🚨 Security First

Working with biological data means the stakes for privacy and security are incredibly high. 
If your contribution touches cryptography, Ed25519 signature verification, or Arweave state evaluation, it will undergo intense scrutiny.

**Never** commit code that logs decrypted Shamir fragments or private keys.

If you find a security vulnerability, **do not open a public issue**. Refer to our [Security Policy](SECURITY.md) for private disclosure instructions.

## 📚 Community

* Check our [GitHub Discussions](https://github.com/orgs/Biological-Sovereignty-Protocol/discussions) for architectural debates.
* Follow the [Ambrosio Institute](https://ambrosio.institute) for protocol-wide announcements.
