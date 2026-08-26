# Altgeld Bitcoin Reserve Roadmap

This roadmap describes the public development direction for the Altgeld Bitcoin Reserve (ABR) repository. It is a working plan, not a promise of funding, adoption, regulatory approval, or implementation by any government body.

## Phase 1 — Public Standard and Documentation

**Status: Active**

Goals:

- Maintain a clear public description of the ABR reserve model
- Keep governance, security, legal-status, and legislative references current
- Distinguish current verified holdings from the 21 BTC long-term goal
- Publish contributor guidance and technical principles
- Create reusable documentation for communities studying the model

Deliverables:

- Governance framework
- Security policy
- Contribution guide
- Technical specification
- Public legislative record
- Change log

## Phase 2 — Proof-of-Reserve Reference Implementation

**Status: Planned / seeking contributors**

Build an open-source, read-only proof-of-reserve reference implementation that can display approved public Reserve data without exposing signing authority or private custody information.

Target capabilities:

- Display one or more approved public Bitcoin addresses or descriptors
- Retrieve confirmed balances from independent Bitcoin data sources
- Show total verified BTC held
- Show current market value with clearly identified price-source timestamps
- Show historical acquisitions and approved releases
- Link displayed transactions to independent block explorers
- Clearly separate verified current holdings from the 21 BTC goal
- Provide machine-readable JSON output for public displays and websites
- Support kiosk/display mode for libraries and community spaces

## Phase 3 — Verification and Data Integrity

**Status: Planned**

Goals:

- Define how ABR publishes approved Reserve addresses or descriptors
- Add validation checks for stale, inconsistent, or unavailable data
- Support more than one independent blockchain-data source where practical
- Publish data-source timestamps and verification status
- Add test fixtures and reproducible verification procedures
- Document limitations of address-based proof-of-reserve

Potential future research:

- Bitcoin Core RPC integration for organizations operating their own node
- Descriptor-based watch-only verification
- Signed public statements that do not expose private keys
- Reproducible reserve snapshots

## Phase 4 — Community Reserve Deployment Kit

**Status: Planned**

Create reusable materials so another community can study and adapt the model without copying ABR-specific custody secrets, names, or legal conclusions.

Possible components:

- Community reserve starter checklist
- Governance decision matrix
- Custody architecture examples
- Public reporting schema
- Proof-of-reserve deployment guide
- Community roundtable template
- Security checklist
- Accessibility checklist
- Policy and legal-review checklist
- Sample public transparency dashboard configuration

## Phase 5 — Public Kiosk and Education Layer

**Status: Concept / seeking partners**

Explore a public-facing display for libraries, community centers, schools, and events.

Possible display modules:

- Live Bitcoin network and price education
- Verified ABR Reserve balance
- Historical reserve milestones
- Explanation of multisignature custody
- History of money and scarcity education
- Plain-language proof-of-reserve walkthrough
- Community-impact reporting after any authorized future releases

The kiosk must remain read-only and must never contain private keys, signing credentials, seed phrases, or custody secrets.

## Phase 6 — Replicable Community Bitcoin Reserve Standard

**Status: Long-term vision**

If the ABR model proves useful, this repository may evolve into a broader open reference standard that communities and municipalities can study, fork, and adapt.

Long-term goals:

- Separate ABR-specific implementation from reusable Community Bitcoin Reserve components
- Publish versioned reference standards
- Document implementation differences across participating communities
- Encourage independent security, legal, governance, and accessibility review
- Make public transparency the default rather than an afterthought

## What This Roadmap Does Not Do

This roadmap does not:

- Authorize any Bitcoin transaction
- Change ABR governance
- Commit any public agency to participate
- Promise that ABR will acquire 21 BTC
- Represent a government-approved technical standard
- Replace legal, tax, accounting, cybersecurity, or custody review

## How to Help

See [CONTRIBUTING.md](CONTRIBUTING.md) and the open GitHub Issues. Contributors are especially welcome in Bitcoin development, frontend engineering, data verification, security review, accessibility, technical writing, civic technology, and public-interest design.
