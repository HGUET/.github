<div align="center">

<img src="https://avatars.githubusercontent.com/u/356244489?v=4" alt="HGUET emblem" width="112" height="112">

# HGUET

### Security before the signature.

**The independent security layer for AI-agent payments on Solana.**

[![Status: Pre-alpha](https://img.shields.io/badge/STATUS-PRE--ALPHA-9b82ff?style=for-the-badge&labelColor=111827)](https://github.com/HGUET/hguet)
[![Solana](https://img.shields.io/badge/ECOSYSTEM-SOLANA-5ae9ce?style=for-the-badge&labelColor=111827)](https://solana.com)
[![Rust](https://img.shields.io/badge/BACKEND-RUST-cbd7e7?style=for-the-badge&labelColor=111827)](https://github.com/HGUET/hguet)

[**Website**](https://hguet.fr) &nbsp;•&nbsp; [**Open-source CLI**](https://github.com/HGUET/hguet) &nbsp;•&nbsp; [**Technical architecture**](https://github.com/HGUET/hguet/tree/main/docs/architecture)

</div>

---

## A valid transaction can still be the wrong payment.

Autonomous agents can submit valid onchain transactions that do not match the payment a user intended: a different recipient, the wrong token, an excessive amount, or unexpected program permissions.

**HGUET is building a pre-signature security checkpoint** to help developers understand transaction effects, verify trusted payment intentions, and decide what to do when evidence is incomplete.

### What we're building

| Open-source HGUET CLI | Optional HGUET Intelligence Cloud |
| :--- | :--- |
| Decode and simulate Solana transactions | Continuously updated network and program signals |
| Compare transfers with independently trusted intent | Threat intelligence with source attribution |
| Apply local policy and spending constraints | Cross-session payment-risk context |
| Return explainable `ALLOW / WARN / DENY / UNKNOWN` decisions | Authenticated enrichment and signed reports |
| Operate without a HGUET account in local mode | Optional prepaid, usage-based access |

> **Development status:** HGUET is **pre-alpha**. These capabilities describe the intended architecture, not a released or audited security product. The sample checks shown on the website are illustrative and must not be relied on to protect live funds.

### Built around clear security boundaries

- **Non-custodial:** no customer wallet private keys, custody, transaction signing or broadcasting.
- **Local-first:** the free CLI is designed to remain independently useful; RPC simulation uses your configured provider.
- **Intent-aware:** a valid blockchain simulation alone does not prove that a payment is authorized.
- **Explicit uncertainty:** `UNKNOWN` means required evidence is unavailable, stale or unsupported — not safe by default.
- **Inspectability:** public CLI behavior, protocol contracts and verdict schemas are documented in the open.
- **Customer-controlled enforcement:** an external wallet or signer must enforce the result before signing.

### Explore the projects

| **Open-source CLI** | **Private Intelligence Server** |
| :--- | :--- |
| **[HGUET / hguet](https://github.com/HGUET/hguet)** | **HGUET / server** *(private)* |
| Rust CLI, transaction analysis, local security policies and public protocol definitions. | Rust Cloud architecture, Solana intelligence, account security and prepaid billing. |
| [Explore the repository](https://github.com/HGUET/hguet) | [Read the public interoperability specification](https://github.com/HGUET/hguet/blob/main/docs/architecture/interoperability.md) |

---

### Support open-source development

If the project is useful to you, voluntary donations help support its development.

**Solana mainnet · Native SOL**

```text
39iqkHNMqncEPp3p52zKwUHnYzk2MJbcaHyY4Hhg2fWC
```

[View donation address on Solscan](https://solscan.io/account/39iqkHNMqncEPp3p52zKwUHnYzk2MJbcaHyY4Hhg2fWC)

*This address accepts voluntary donations only. It is not an address for HGUET Cloud subscriptions, service credits, or USDC invoices. Always verify the network and complete wallet address before transferring.*

---

<div align="center">

### Secure the intent. Verify the transaction.

**Free to verify locally. Optional deeper intelligence.**

[GitHub](https://github.com/HGUET/hguet) &nbsp;•&nbsp; [hguet.fr](https://hguet.fr)

<sub>HGUET is an independent project in the Solana ecosystem. It is not affiliated with or endorsed by the Solana Foundation.</sub>

</div>
