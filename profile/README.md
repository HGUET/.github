<div align="center">

# HGUET

### Security before the signature.

**Open-source, pre-signature security research for AI-initiated payments on Solana.**

[![Stage](https://img.shields.io/badge/stage-pre--alpha-9b82ff?style=flat-square)](https://github.com/HGUET/hguet)
[![Core](https://img.shields.io/badge/core-Rust-6ee7d2?style=flat-square)](https://github.com/HGUET/hguet)
[![Network](https://img.shields.io/badge/network-Solana-a68cff?style=flat-square)](https://solana.com/)
[![Release](https://img.shields.io/badge/release-not%20yet-8b9bb7?style=flat-square)](https://github.com/HGUET/hguet/releases)

[**Project website**](https://hguet.fr/) · [**Public Rust CLI**](https://github.com/HGUET/hguet) · [**Architecture**](https://github.com/HGUET/hguet/tree/main/docs/architecture) · [**Protocol v1**](https://github.com/HGUET/hguet/tree/main/protocol/v1)

</div>

---

## A valid Solana transaction is not necessarily an authorized payment

A successful simulation, a valid signature, or an agent's assertion of intent cannot establish that a transfer matches **the user's independent authorization**. HGUET is being built to inspect transaction effects, check separately trusted payment intentions, apply restrictive local policy, and make uncertainty visible **before customer-controlled signing**.

The goal is **a security checkpoint, not an autonomous wallet or a guarantee of safety**.

## What exists in source today

| Workstream | Present implementation | Boundary |
| :--- | :--- | :--- |
| **Public Rust CLI** | Offline legacy/v0/v1 transaction parsing; signature and signed-intent verification; direct SOL and selected SPL Token / Token-2022 checks; restrictive policy; structured findings | **Pre-alpha source, no stable release.** Does not certify complete transaction effects |
| **Opt-in Solana RPC** | Read-only simulation, account and token observations, limited CPI analysis and source-aware effect correlation | Provider-derived and non-atomic evidence is **advisory**, not execution proof |
| **Signer boundary** | Separate-process, Linux sandbox and replay-protection prototypes | **BLOCK-only.** No wallet SDK, signing, broadcast or automatic authorization |
| **Private Rust server** | Pricing and signed-report primitives; PostgreSQL paid-job storage; two-origin finalized **Devnet** payment verification; bounded history worker; operator refund-review workflow | Unreleased; operator-driven pieces are **not** a live end-to-end Cloud service |
| **Cloud transport prototype** | Loopback-only TLS 1.3 / Protobuf with post-quantum-capable cryptography and narrowly scoped completed-result retrieval | No Internet-facing paid API, new paid-job admission or public service |

**Current local decision boundary:** the public CLI intentionally produces restrictive **DENY** or **UNKNOWN** results, **never an automatic ALLOW to sign**. A trusted external wallet/signer must remain the enforcement boundary.

The private server prototype uses **anonymous, native-SOL pay-per-check on sandbox Devnet**, not customer accounts, subscriptions, USDC credits or production Mainnet billing. Its parts are not connected into a released payment-to-assessment workflow. Server verification, real cross-platform interoperability, independent audit and deployment approval remain outstanding.

## Architecture and trust model

\`\`\`text
Agent proposes transaction
          |
          v
  HGUET open-source CLI  <--- independently trusted PaymentIntent + local policy
      |          |
      |          +---- opt-in read-only Solana RPC evidence
      v
 DENY / UNKNOWN  ---> customer-controlled signer remains the final gate

Future optional path (NOT available as a public service):
 CLI --- authenticated Cloud protocol ---> HGUET private Devnet research backend
                                             pricing / provenance / signed artifacts
\`\`\`

- **Non-custodial:** HGUET does not hold funds or request wallet private keys.
- **Local-first:** offline inspection works without a HGUET account; RPC is explicitly configured and may disclose queried transaction/account data to that provider.
- **Trust separation:** an AI agent cannot manufacture its own authorization by supplying a "trusted" intent, policy or signing key.
- **Explicit uncertainty:** a simulation, a partial instruction decode or stale/opaque source evidence must not silently become permission to pay.
- **Inspectable contracts:** the public [protocol schemas](https://github.com/HGUET/hguet/tree/main/protocol/v1), [architecture](https://github.com/HGUET/hguet/tree/main/docs/architecture) and [implementation notes](https://github.com/HGUET/hguet/tree/main/docs/implementation) are open for review.

## Repositories

| Repository | Scope | Visibility |
| :--- | :--- | :--- |
| [**HGUET/hguet**](https://github.com/HGUET/hguet) | Rust CLI, local policy, restricted signer research, public protocol and tests | Public |
| **HGUET/server** | Rust intelligence, Devnet settlement, PostgreSQL, PQ transport and operational tooling | Private |
| **HGUET/web** | Static website source; product explanations and illustrative demo | Private |
| [**HGUET/.github**](https://github.com/HGUET/.github) | This organization profile | Public |

The [website](https://hguet.fr/) describes the direction of the project; its interactive examples **do not execute checks or process payments**.

## Development and release status

**Pre-alpha · 16 November 2026.** Source code and automated checks exist; there are **no published HGUET product releases**, no independently audited security approval and no production Cloud endpoint. Public CLI CI has passed on recent revisions, while private server GitHub Actions has not completed its required validation. Do not use this project to approve transfers of live funds.

We welcome source-level discussion, test cases and adversarial reviews through the [public repository](https://github.com/HGUET/hguet). The roadmap is research and implementation work, **not a promise of release dates or a security SLA**.

## Support development (optional)

Donations can support open-source work. The address below is for **voluntary native SOL on Solana Mainnet only**, **not** a Cloud invoice or service-credit address.

\`\`\`text
39iqkHNMqncEPp3p52zKwUHnYzk2MJbcaHyY4Hhg2fWC
\`\`\`

[View on Solscan](https://solscan.io/account/39iqkHNMqncEPp3p52zKwUHnYzk2MJbcaHyY4Hhg2fWC) · Always verify the full address and network independently before sending.

---

<div align="center">

**Secure the intent. Verify the transaction. Keep signing under human-controlled policy.**

<sub>HGUET is an independent Solana ecosystem project. It is not affiliated with or endorsed by the Solana Foundation.</sub>

</div>
