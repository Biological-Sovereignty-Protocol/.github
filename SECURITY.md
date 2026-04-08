# Security Policy

Thank you for helping keep the Biological Sovereignty Protocol (BSP) and its users secure.

Because BSP deals with highly sensitive human biological data, clinical records, and cryptographic identity (BEOs), we take security vulnerabilities extremely seriously.

## 🛡️ Scope of Security

We are particularly interested in vulnerabilities related to:
* **SmartWeave Contract flaws** that could bypass ConsentToken verification.
* **Cryptographic edge cases** modifying Ed25519 signature validation.
* **Social Recovery (Shamir Secret Sharing) leaks**, specifically in the `bsp-sdk` or the `bsp-registry-api` guardian flow.
* **On-chain State Manipulation** allowing unauthorized modification of Biological Entity Objects (BEO).

## 🚨 Reporting a Vulnerability

If you discover a security vulnerability in this repository or anywhere within the Biological Sovereignty Protocol ecosystem, please report it immediately through the [GitHub Security Advisory process](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability).

Alternatively, you can email our core security team directly at **security@biologicalsovereigntyprotocol.com**.

### ⚠️ IMPORTANT: 
Please **do not** report security vulnerabilities through public GitHub issues, discussions, or pull requests. Exposing a flaw publicly before it is patched puts human biological data at theoretical risk.

## 📝 What to Include

To help us triage and respond quickly, please include:

- A clear description of the vulnerability.
- Step-by-step instructions to reproduce the issue.
- The repository and specific file/line where the issue exists (e.g., `bsp-sdk-typescript/src/beo/Recovery.ts`).
- The potential impact on BEOs or IEOs.
- Proof of Concept (PoC) code if available.

We pledge to respond to all security reports within 48 hours.
