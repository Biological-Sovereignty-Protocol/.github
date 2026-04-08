<div align="center">

<a href="https://biologicalsovereigntyprotocol.com">
  <img src="assets/bsp-logo-dark.png" alt="Biological Sovereignty Protocol" width="560" />
</a>

<br /><br />

### The open protocol for sovereign biological data.

BSP is a neutral, open-source standard that enables any wearable, laboratory, health platform, or AI system to exchange biological data through a shared, structured, and consent-based language — where the individual always remains the owner.

<br />

[![Protocol](https://img.shields.io/badge/BSP-v0.2_Specification-0066CC?style=flat-square)](https://github.com/Biological-Sovereignty-Protocol/bsp-spec)
[![License Spec](https://img.shields.io/badge/Spec-CC_BY_4.0-lightgrey?style=flat-square)](https://creativecommons.org/licenses/by/4.0/)
[![License SDK](https://img.shields.io/badge/SDK-Apache_2.0-blue?style=flat-square)](https://github.com/Biological-Sovereignty-Protocol/bsp-sdk-typescript/blob/main/LICENSE)
[![npm](https://img.shields.io/npm/v/@bsp/sdk?style=flat-square&label=%40bsp%2Fsdk)](https://www.npmjs.com/package/@bsp/sdk)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://github.com/Biological-Sovereignty-Protocol/bsp-sdk-typescript)
[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://github.com/Biological-Sovereignty-Protocol/bsp-sdk-python)
[![Built on Arweave](https://img.shields.io/badge/Permanent_Storage-Arweave-222222?style=flat-square)](https://arweave.org)

<br />

[**Specification**](https://github.com/Biological-Sovereignty-Protocol/bsp-spec) · [**Documentation**](https://biologicalsovereigntyprotocol.com) · [**TypeScript SDK**](https://github.com/Biological-Sovereignty-Protocol/bsp-sdk-typescript) · [**Python SDK**](https://github.com/Biological-Sovereignty-Protocol/bsp-sdk-python) · [**CLI**](https://github.com/Biological-Sovereignty-Protocol/bsp-cli) · [**AI / MCP**](https://github.com/Biological-Sovereignty-Protocol/bsp-mcp)

</div>

---

## The Problem

Every blood test, wearable reading, genomic result, and clinical record lives in a different system — owned by a different company, locked in a different format, invisible to everything else.

The patient does not own their data. The doctor cannot read the lab's output. The AI cannot access the hospital's records. The longevity protocol cannot execute without copy-pasting PDFs.

Three structural failures drive this:

| Failure | What it means |
|---|---|
| **Fragmentation** | Every health company builds proprietary silos. No common language exists. No interoperability. |
| **Sovereignty loss** | Biological data is owned by corporations and institutions — not by the person it belongs to. |
| **AI readiness gap** | AI has the potential to transform medicine. But only with structured, standardized, accessible data. Today that data does not exist at scale. |

BSP is the infrastructure layer that solves all three.

---

## What BSP Is

BSP is a **neutral open protocol** — like HTTP for the web, or SMTP for email, but for biological data.

It defines a complete, interoperable standard for:

| Object | Description |
|---|---|
| **BEO** — Biological Entity Object | The sovereign digital identity of a human being. Lifelong, cryptographically secured, individually owned. |
| **IEO** — Institutional Entity Object | The verified identity of any lab, hospital, clinic, wearable, or health platform. |
| **BioRecord** | The universal format for a single biological measurement — from fasting glucose to epigenetic clock scores. |
| **ConsentToken** | Granular, cryptographic permission granted by the individual to an institution. Revocable at any time. |
| **BSP Exchange** | The protocol for requesting, submitting, and reading biological records between systems. |
| **Biomarker Taxonomy** | 200+ standardized codes across 4 levels covering the complete spectrum of measurable human biology. |

BSP does not analyze data. BSP does not make medical decisions. BSP is the transport layer. Intelligence systems like AVA operate above it.

---

## Architecture

```
  ┌─────────────────────────────────────────────────────────────┐
  │         INTELLIGENCE LAYER  (above the protocol)            │
  │     AVA · SVA · third-party algorithms · health apps        │
  │          not defined by BSP — consumes BSP data             │
  └────────────────────────────┬────────────────────────────────┘
                               │  reads / writes via BSP
┌──────────────────────────────▼──────────────────────────────────┐
│                      BSP PROTOCOL STACK                          │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│  LAYER 3 — BSP-EXCHANGE                                          │
│  How data moves between systems                                  │
│  Request · Response · ConsentToken · AccessControl               │
│                                                                  │
│  LAYER 2 — BSP-DATA                                              │
│  What data contains                                              │
│  BioRecord · Biomarker Taxonomy (L1 Core → L4 Device)           │
│                                                                  │
│  LAYER 1 — BSP-IDENTITY                                          │
│  Who holds the data                                              │
│  BEO (individual) · IEO (institution) · .bsp domains            │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
  Stored on Arweave — permanent, decentralized, immutable
  BEORegistry · IEORegistry · DomainRegistry · AccessControl
```

---

## Biomarker Taxonomy

BSP defines the most comprehensive open biomarker taxonomy ever codified — covering the full spectrum of measurable human biology.

| Level | Name | Scope | Categories |
|---|---|---|---|
| **L1 — Core** | Advanced longevity | Biological aging, epigenetics, telomere length, methylation clocks | 9 |
| **L2 — Standard** | Routine laboratory | Metabolic, hormonal, hematology, lipid panels — performed worldwide | 9 |
| **L3 — Extended** | Specialized clinical | Genomics, toxicology, microbiome, inflammatory markers | 6 |
| **L4 — Device** | Continuous biometric | Wearable sensor streams (HRV, SpO2, sleep, glucose CGM) | 1 |

Every biomarker has a standardized code: `BSP-{CATEGORY}-{NUMBER}` (e.g., `BSP-GL-001` = Fasting Glucose).

Browse the full taxonomy → [`bsp-spec/spec/taxonomy/`](https://github.com/Biological-Sovereignty-Protocol/bsp-spec/tree/main/spec/taxonomy)

---

## Quick Start

### TypeScript / JavaScript

```bash
npm install bsp-sdk
```

```typescript
import { BEOClient, AccessManager, BioRecordBuilder, ExchangeClient } from 'bsp-sdk'

// 1. Individual creates their sovereign biological identity
const { beo, keyPair } = await new BEOClient().create({ domain: 'andre.bsp' })

// 2. Grant consent to a laboratory — granular, revocable
const token = await new AccessManager({ beo, privateKey: keyPair.privateKey })
  .grantConsent({
    ieoId: 'sunrise-lab.bsp',
    scope: {
      intents: ['SUBMIT_RECORD', 'READ_RECORDS'],
      categories: ['METABOLIC', 'HORMONAL'],
      levels: ['STANDARD'],
      period: null,
      max_records: null,
    },
  })

// 3. Lab builds and submits a signed BioRecord
const record = new BioRecordBuilder()
  .beoId(beo.beo_id)
  .biomarker('BSP-GL-001')   // Fasting glucose — L2 Standard
  .value(94).unit('mg/dL')
  .timestamp(new Date().toISOString())
  .confidence(0.99)
  .sign(labPrivateKey)
  .build()

const result = await new ExchangeClient({ ieoId: 'sunrise-lab.bsp', privateKey: labPrivateKey })
  .submit(record, token)

console.log(result.arweave_txs[0])  // Permanent, immutable record on Arweave
```

### Python

```bash
pip install bsp-sdk
```

```python
from bsp_sdk import BioRecordBuilder, AccessManager, ExchangeClient

# Build a blood test result
record = (BioRecordBuilder()
    .beo_id("patient-beo-id")
    .biomarker("BSP-GL-001")
    .value(94).unit("mg/dL")
    .timestamp("2026-02-24T08:30:00Z")
    .confidence(0.99)
    .build())

# Submit with patient consent
token = AccessManager(ieo_id="my-lab.bsp").wait_for_approval(request_id)
result = ExchangeClient(ieo_id="my-lab.bsp").submit(record, token)
print(result["arweave_tx"])  # Permanent record
```

### CLI

```bash
npx bspctl create andre.bsp           # Create biological identity
npx bspctl consent grant <beo> <ieo> --intents SUBMIT_RECORD --days 365
npx bspctl export <beo> --token <tok> --format FHIR_R4
npx bspctl destroy <beo> --confirm    # LGPD/GDPR erasure
```

### AI Integration — Claude via MCP

Add BSP to your Claude Desktop `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "bsp": {
      "command": "npx",
      "args": ["bsp-mcp"],
      "env": { "BSP_BEO_DOMAIN": "your-name.bsp" }
    }
  }
}
```

Then ask Claude: *"What do my last blood test results say about my longevity markers?"*

---

## Repositories

| Repository | Description | Status |
|---|---|---|
| [**bsp-spec**](https://github.com/Biological-Sovereignty-Protocol/bsp-spec) | Protocol specification — BEO, IEO, BioRecord formats, biomarker taxonomy, governance model | `v0.2 Draft` |
| [**bsp-sdk-typescript**](https://github.com/Biological-Sovereignty-Protocol/bsp-sdk-typescript) | Official TypeScript/JavaScript SDK — `npm install bsp-sdk` | `v1.0.0` |
| [**bsp-sdk-python**](https://github.com/Biological-Sovereignty-Protocol/bsp-sdk-python) | Official Python SDK — `pip install bsp-sdk` | `v1.0.0` |
| [**bsp-cli**](https://github.com/Biological-Sovereignty-Protocol/bsp-cli) | Official CLI — manage BEOs, IEOs, consent, and health data from the terminal | `v1.0.0` |
| [**bsp-mcp**](https://github.com/Biological-Sovereignty-Protocol/bsp-mcp) | MCP server — connect Claude, ChatGPT, and other AI systems natively to BSP data | `v1.0.0` |
| [**bsp-id-web**](https://github.com/Biological-Sovereignty-Protocol/bsp-id-web) | Reference web application for BSP identity creation, consent management, and dashboard | `v0.1` |
| [**bsp-docs**](https://github.com/Biological-Sovereignty-Protocol/bsp-docs) | Complete documentation — quickstarts, implementation guides, API reference, whitepaper | Live |

---

## Design Principles

| Principle | What it means |
|---|---|
| **Open** | The specification is free. No licensing fees. No permission needed. Implement it, build on it, fork it. |
| **Neutral** | BSP carries data — it does not analyze it. No algorithmic bias. No health philosophy embedded in the protocol. |
| **Sovereign** | Every record belongs to a biological individual. Data ownership is enforced at the protocol level, not by policy. |
| **Extensible** | Versioned and backward-compatible. New biomarkers and data types can be added without breaking existing implementations. |
| **Permanent** | Records are written to Arweave. They cannot be deleted, altered, or lost — by anyone, including Ambrósio. |
| **AI-ready** | Structured, standardized, machine-readable by design. Any AI system can consume BSP data directly via the SDK or MCP. |

---

## Who BSP Is For

**Developers** building health apps, longevity platforms, or patient-facing tools that need interoperable biological data.

**Laboratories and clinics** that want to submit structured exam results with patient consent — without proprietary integrations.

**Health platforms** that want to become interoperable with any other BSP-compatible system in the world.

**AI researchers and engineers** who need structured, high-quality biological data for training, analysis, or real-time inference.

**Individuals** who want sovereign control over their own biological history and the ability to share it on their own terms.

---

## Contributing

BSP evolves through **Biological Improvement Proposals (BIPs)** — a community-driven governance process modeled after established open standards (BIPs, EIPs, RFCs).

1. Read the [governance model](https://github.com/Biological-Sovereignty-Protocol/bsp-spec/blob/main/spec/governance.md)
2. Use the [BIP template](https://github.com/Biological-Sovereignty-Protocol/bsp-spec/blob/main/bip/BIP-0000-template.md)
3. Open a Pull Request in `bsp-spec`

Protocol changes require community discussion and multi-signature approval from the Ambrósio Institute council.

For SDK contributions, see `CONTRIBUTING.md` in each repository.

---

## License

**Specification** — [Creative Commons Attribution 4.0 (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
Anyone may implement, build on, or distribute the BSP specification without fees or permission.

**SDKs** — [Apache License 2.0](https://apache.org/licenses/LICENSE-2.0)

---

<div align="center">

**Published and governed by the [Ambrósio Institute](https://ambrosioinstitute.org)**

[biologicalsovereigntyprotocol.com](https://biologicalsovereigntyprotocol.com) &nbsp;·&nbsp; [Documentation](https://biologicalsovereigntyprotocol.com/developers) &nbsp;·&nbsp; [Discussions](https://github.com/orgs/Biological-Sovereignty-Protocol/discussions)

<br />

*The protocol belongs to the world. The intelligence belongs to Ambrósio. The sovereignty belongs to the individual.*

</div>
