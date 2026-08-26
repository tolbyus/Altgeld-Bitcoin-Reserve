# ABR Public Technical Specification

**Status:** Draft reference specification

This document describes a proposed technical architecture for the public transparency and proof-of-reserve layer of the Altgeld Bitcoin Reserve (ABR). It does not define private custody procedures, signing operations, or legal authority.

## 1. Purpose

The technical system should make it easy for a resident, developer, journalist, donor, policymaker, or independent reviewer to answer basic public questions:

- How much Bitcoin is currently verified as part of the Reserve?
- Which approved public Bitcoin addresses or watch-only descriptors are being used for verification?
- When was the data last checked?
- What transactions changed the Reserve balance?
- How does the verified balance compare with ABR's long-term 21 BTC goal?
- Can the information be independently checked against the Bitcoin network?

The system should increase transparency without increasing custody risk.

## 2. Core Design Rule

**The public transparency system must be read-only.**

It must never require or store:

- Seed phrases
- Private keys
- Hardware-wallet PINs
- Recovery material
- Signing credentials
- Partially signed Bitcoin transactions unless separately approved for controlled public verification
- Physical custody locations
- Sensitive keyholder procedures

The public application must not be capable of moving Reserve Bitcoin.

## 3. Proposed Architecture

A reference implementation may use the following layers:

### A. Reserve Registry

A public, versioned data file containing approved information such as:

- Reserve identifier
- Community name
- Approved public Bitcoin address, addresses, or watch-only descriptors
- Effective date
- Status
- Optional public transaction annotations

The registry should be human-readable and machine-readable.

Example fields:

```json
{
  "reserve": "Altgeld Bitcoin Reserve",
  "network": "bitcoin-mainnet",
  "verification_targets": [],
  "goal_btc": 21,
  "last_registry_update": "YYYY-MM-DD"
}
```

The example contains no live custody information and is illustrative only.

### B. Bitcoin Data Adapter

A read-only service that retrieves blockchain data for the approved verification targets.

Preferred design:

1. Support a Bitcoin Core node or another independently operated Bitcoin data source.
2. Permit fallback to reputable public blockchain-data providers when necessary.
3. Record source and timestamp with each verification result.
4. Avoid silently combining inconsistent results.
5. Surface errors when sources disagree or data cannot be verified.

### C. Verification Engine

The verification engine should calculate and expose:

- Confirmed BTC balance
- Unconfirmed balance, if displayed, clearly separated from confirmed funds
- Last verified block height
- Verification timestamp
- Data source
- Transaction history relevant to the published verification targets
- Any detected data-quality warnings

No dollar-value calculation should be treated as proof that Bitcoin exists. Bitcoin network verification and fiat price display are separate functions.

### D. Price Adapter

A separate component may retrieve BTC/USD pricing for educational display.

Requirements:

- Identify the price source
- Show the timestamp
- Treat the price as informational and volatile
- Keep price failure from breaking proof-of-reserve verification

### E. Public API

A small public API or static JSON endpoint may expose verified data.

Suggested fields:

```json
{
  "verified_btc": null,
  "goal_btc": 21,
  "verification_timestamp": null,
  "block_height": null,
  "bitcoin_data_source": null,
  "btc_usd": null,
  "price_timestamp": null,
  "status": "unverified"
}
```

A client must never substitute `goal_btc` for `verified_btc`.

### F. Public Dashboard / Kiosk

The public interface should be understandable without Bitcoin expertise.

Suggested primary display:

- **Verified Reserve:** current BTC verified
- **Long-term goal:** 21 BTC
- **Last verified:** date/time and block height
- **Current value:** clearly labeled market estimate
- **Transactions:** independently checkable history
- **How to verify:** plain-language explanation

Accessibility requirements should include readable type, keyboard navigation, descriptive labels, high information clarity, and a layout usable on both mobile devices and public displays.

## 4. Proof-of-Reserve Meaning

For this project, proof-of-reserve should mean that the public can independently verify Bitcoin associated with ABR's approved public verification targets on the Bitcoin network.

Address-based verification has limitations. Seeing Bitcoin at a public address does not, by itself, prove every legal, governance, or beneficial-ownership claim about that Bitcoin. Public documentation should state those limitations clearly.

Future contributors may research stronger public-verification methods that do not expose private keys or weaken custody.

## 5. Governance Boundary

Software verification and governance authorization are separate.

The repository's public software may display an approved transaction after it occurs, but software must not determine whether a community release is authorized.

The Reserve Governance Framework controls ABR's policy model. A code change or pull request cannot authorize a release, appoint a keyholder, or alter the Reserve Policy.

## 6. Security Model

### Threats to consider

- False reserve addresses being published
- Compromised data-provider responses
- Stale data presented as current
- Price feeds being confused with reserve verification
- Malicious or misleading transaction annotations
- Accidental exposure of private information
- Web application compromise
- Dependency or supply-chain attacks
- Social engineering directed at keyholders or contributors

### Required safeguards

- Read-only architecture
- No signing keys in the public application
- Version-controlled public registry
- Source and timestamp disclosure
- Dependency review
- Input validation
- Clear error states
- No secrets committed to GitHub
- Reproducible verification where practical

Security concerns should be reported according to [../SECURITY.md](../SECURITY.md), not through a public issue when disclosure could create risk.

## 7. Privacy

Public transparency should focus on Reserve-level information, not unnecessary personal data.

Do not expose:

- Resident financial information
- Donor identities unless intentionally and lawfully public
- Keyholder home addresses or private contact information
- Device locations
- Recovery arrangements
- Sensitive government or partner information

## 8. Suggested Technology-Neutral Interfaces

Contributors are free to propose languages and frameworks, but the reference design should favor:

- Simple deployment
- Auditable code
- Minimal dependencies
- Read-only Bitcoin integrations
- Open data formats
- Testability
- Accessibility
- Compatibility with static or low-cost public hosting when possible

A future implementation may include a backend service, a static-site build process, or direct read-only calls to approved infrastructure. Architectural choices should be documented before production use.

## 9. Testing Expectations

A production-quality implementation should include tests for:

- Correct BTC unit conversion
- Multiple addresses or verification targets
- Zero-balance addresses
- Provider timeouts
- Provider disagreement
- Stale price data
- Stale blockchain data
- Reorganizations where relevant
- Invalid configuration
- Goal-versus-current-balance display separation
- Accessibility-critical UI behavior

Tests must use fixtures, public test data, signet/testnet data, or approved public mainnet data. Never use private custody material.

## 10. Proposed Repository Structure

A future implementation could use a structure similar to:

```text
app/
  api/
  dashboard/
  components/
lib/
  bitcoin/
  pricing/
  verification/
config/
  reserve-registry.json
tests/
docs/
```

This is a suggested organization, not a mandated framework.

## 11. Deployment Principles

Before a public production deployment:

- Security review should be completed
- Verification sources should be documented
- Public data should be approved for publication
- Error and outage behavior should be tested
- No secrets should be present in client-side code or repository history
- A rollback and maintenance process should exist

The public proof-of-reserve system should never be placed in the transaction-signing path.

## 12. Open Technical Questions

Contributors are invited to help evaluate:

- Best approach for Bitcoin Core-based public verification
- Best public fallback sources
- Address list versus watch-only descriptor publication
- Reproducible reserve snapshots
- Data signing or attestation methods that do not create custody risk
- Kiosk/offline resilience
- Public API schema and versioning
- Independent third-party mirrors
- Accessible explanations of Bitcoin confirmations and transaction history

## 13. Non-Authority Notice

This specification is a public technical draft. It does not modify ABR's governing documents, authorize custody actions, represent legal advice, or constitute a government-approved standard.
