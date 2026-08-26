# Contributing to the Altgeld Bitcoin Reserve

Thank you for your interest in the Altgeld Bitcoin Reserve (ABR).

ABR welcomes thoughtful public-interest contributions from Bitcoin developers, designers, security researchers, policy researchers, educators, community members, lawyers, accessibility reviewers, and technical writers.

The goal of this repository is not only to publish ABR's framework, but to help develop transparent, reusable infrastructure that communities can study and adapt.

## Where Help Is Most Useful

Current contribution areas include:

- Public proof-of-reserve dashboards and displays
- Bitcoin address and transaction verification tools
- Read-only blockchain data integrations
- Public reporting and transparency tooling
- Community reserve deployment documentation
- Security and threat-model review
- Accessibility and plain-language documentation
- Bitcoin, financial-literacy, and digital-literacy education
- Governance and policy research
- Replication tools for other communities and municipalities

See [ROADMAP.md](ROADMAP.md) and [docs/TECHNICAL-SPEC.md](docs/TECHNICAL-SPEC.md) for the current direction.

## How to Contribute

1. Read the README, Reserve Governance Framework, Security Policy, and Technical Specification.
2. Review open GitHub Issues before beginning substantial work.
3. Open an Issue for a proposed feature, research question, or major change so the scope can be discussed publicly.
4. Keep pull requests focused on one problem at a time.
5. Explain what changed, why it changed, and any security, governance, privacy, or accessibility tradeoffs.
6. Do not represent a draft contribution as formally adopted ABR policy.

Small corrections such as spelling, formatting, broken links, and accessibility fixes may be submitted directly.

## Technical Principles

Contributions to ABR technical infrastructure should follow these principles:

- **Bitcoin only.** Do not add altcoin, token, staking, yield, lending, leverage, or speculative-trading functionality.
- **Read-only by default.** Public dashboards should observe and verify Reserve information, not hold signing authority.
- **No private-key exposure.** Public software must never require seed phrases, private keys, recovery material, or custody secrets.
- **Independent verification.** Where practical, public claims should be verifiable against Bitcoin network data rather than trusted only because ABR says they are true.
- **Clear separation of roles.** Governance authorization, custody execution, public reporting, and software display are different functions.
- **Privacy by design.** Do not expose unnecessary personal information about residents, donors, keyholders, or staff.
- **Accessibility.** Public-facing tools should be understandable and usable by nontechnical community members.
- **Reusability.** Prefer designs that can later be adapted by another community without copying ABR-specific secrets or infrastructure.

## Governance Changes

A GitHub pull request cannot, by itself:

- Change the Reserve Policy
- Authorize a Bitcoin transaction
- Appoint or remove a keyholder
- Approve a community release
- Amend the governing documents of ABR Wealth Fund DAO LLC or ABR Foundation

Proposed policy changes should clearly identify:

1. The provision affected
2. The proposed language
3. The reason for the change
4. Risks and tradeoffs
5. Whether formal governance approval would be required

## Security

Do not report security vulnerabilities publicly. Follow [SECURITY.md](SECURITY.md).

Never include private keys, seed phrases, recovery material, credentials, personal information, physical custody locations, or sensitive signing procedures in an issue, pull request, screenshot, or repository file.

Do not test a vulnerability by attempting to access, control, sign for, or move Reserve funds.

## Reserve Claims

The **21 BTC figure is ABR's long-term goal, not its current balance**. Contributions must never describe the goal as current holdings.

Any public proof-of-reserve component should distinguish clearly between:

- Current verified BTC held
- Current market value
- Historical acquisitions and releases
- The long-term 21 BTC objective

## Contribution Licensing

Unless a pull request clearly states otherwise and ABR agrees in writing:

- Documentation and other non-code contributions are submitted under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).
- Software source-code and script contributions are submitted under the [MIT License](LICENSES/MIT.txt) and should be clearly identified as MIT-licensed.

By submitting a contribution, you confirm that you created it or otherwise have the right to submit it under the applicable license. See [LICENSE](LICENSE) for the repository's full licensing notice.

## Community Standard

Treat residents, contributors, reviewers, public officials, and outside organizations with respect. Critique ideas and code rather than people. See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).
