<div align="center">
  <img src="assets/bsp-logo-dark.png" alt="Biological Sovereignty Protocol" width="600" />
</div>

<div align="center">
  <h3>A protocol for absolute ownership, granular consent, and frictionless exchange of human biological data.</h3>
</div>

<div align="center">
  <a href="https://biologicalsovereigntyprotocol.com">Website</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://biologicalsovereigntyprotocol.com/developers/sdk-reference">Documentation</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://github.com/Ambrosio-Institute/BSP">Specification</a>
</div>

<br/>

## 🧬 What is the Biological Sovereignty Protocol (BSP)?

BSP is a decentralized baseline for the future of precision medicine and longevity. Built natively on **Arweave** and **SmartWeave**, it resolves the healthcare data silo problem by introducing true cryptographic ownership over biological, genomic, and clinical records.

Instead of institutional EHRs walling off patient data, BSP creates **Biological Entity Objects (BEOs)** owned exclusively by the individual’s private key. Institutions (**IEOs**) request access and are granted cryptographically signed **ConsentTokens** with explicit temporal constraints and granular intents.

## 🚀 Repositories

### Core Implementation
* [**bsp-sdk-typescript**](https://github.com/Biological-Sovereignty-Protocol/bsp-sdk-typescript) — The official TypeScript SDK for Node.js and browser applications. The primary gateway to read and write to the protocol.
* [**bsp-sdk-python**](https://github.com/Biological-Sovereignty-Protocol/bsp-sdk-python) — The official Python SDK. Designed for researchers, data science applications, and offline analytics.
* [**bsp-mcp**](https://github.com/Biological-Sovereignty-Protocol/bsp-mcp) — Model Context Protocol (MCP) server integration. Empowers AI Assistants to natively interact with an individual's biological records.
* [**bsp-api-reference**](https://github.com/Biological-Sovereignty-Protocol/bsp-api-reference) — Open specification and REST proxies for legacy non-blockchain environments.

### Core Protocol Contracts (Ambrosio Institute)
*Note: Governance and core infrastructure contracts are stewarded by the [Ambrosio Institute](https://github.com/Ambrosio-Institute).*
* [**bsp-registry**](https://github.com/Ambrosio-Institute/bsp-registry) — The immutable SmartWeave protocol contracts (`BEORegistry`, `IEORegistry`, `AccessControl`, `DomainRegistry`, `Governance`).
* [**bsp-registry-api**](https://github.com/Ambrosio-Institute/bsp-registry-api) — The official protocol relayer service for gas abstraction and off-chain Guardian Notification flows.

## 🏗️ Architecture at a Glance

| Component | Description |
| :--- | :--- |
| **BEO** <br>*(Biological Entity Object)* | Abstract digital identity for humans (`andre.bsp`). Exclusively controlled by the owner's private key. Supports advanced Social Recovery (Shamir Secret Sharing) ensuring data is never lost. |
| **IEO** <br>*(Institutional Entity Object)* | Regulated entities (hospitals, AI platforms, wearables). Must pass Governance certification to issue data or request ConsentTokens. |
| **ConsentTokens** | Non-transferable digital permits issued by a BEO to an IEO, detailing precise `intents` (ex: `READ_BASIC_BIO`, `WRITE_CLINICAL`) and `periods` of validity. |
| **BioRecords** | AES-GCM encrypted data blobs permanently stored on Arweave. The BEO key is the ultimate anchor of decryption. |

## 🌟 Contributing

The Biological Sovereignty Protocol is an open standard. We welcome contributors who share the vision of an interoperable, sovereign future for health data.

* Read our [Contribution Guide](https://biologicalsovereigntyprotocol.com/developers/contributing)
* Join the discussion in our [Issues](https://github.com/Biological-Sovereignty-Protocol/bsp-sdk-typescript/issues)
* Explore the [SmartWeave architecture](https://github.com/Ambrosio-Institute/bsp-registry/tree/main/contracts)

<br/>

<div align="center">
  <img src="https://img.shields.io/badge/Arweave-000000?style=for-the-badge&logo=arweave&logoColor=white" />
  <img src="https://img.shields.io/badge/SmartWeave-111111?style=for-the-badge&logo=smartcontracts&logoColor=white" />
  <img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" />
</div>
<div align="center">
  <i>Maintained by the Ambrosio Institute</i>
</div>
