# Change Log

All material changes to the public ABR framework should be recorded here.

## August 26, 2026 - Open-Source Development Expansion

### Added

- Public development roadmap for proof-of-reserve, verification, kiosk, and Community Bitcoin Reserve replication work
- Draft public technical specification for a read-only transparency architecture
- Contributor code of conduct
- Expanded contributor guidance for Bitcoin developers, security researchers, designers, educators, policy researchers, and civic technologists
- Developer and contributor pathway in the main README
- Initial public GitHub workstreams for proof-of-reserve dashboard development, Reserve Registry schema, Bitcoin Core verification, threat modeling, kiosk design, and a Community Bitcoin Reserve deployment starter kit

### Technical Boundary

- Public transparency software is defined as read-only and separate from the Reserve transaction-signing path.
- Public technical tooling must not request, store, or expose seed phrases, private keys, recovery material, signing credentials, or sensitive custody information.
- Public interfaces must continue to distinguish verified current holdings from the 21 BTC long-term goal.

## August 19, 2026 - Split Repository Licensing

### Changed

- Documentation and other non-code materials are designated CC BY-NC-SA 4.0.
- Software source code and scripts are MIT-licensed only when expressly identified as such.
- Added clear contribution-licensing rules and commercial-licensing contact information.
- Preserved notice that permissions already granted for earlier MIT-licensed repository versions are not revoked.

## August 2026 - Governance Framework Refresh

### Added

- August 2026 Reserve, Governance & Community Distribution Framework in PDF and accessible Markdown formats
- Prominent disclosure that 21 BTC is a long-term goal, not the current balance
- ABR Wealth Fund DAO LLC and ABR Foundation role separation
- Five-year initial hold framework
- Optional annual release ceiling of up to 0.21 BTC after the hold
- 2-of-3 standard multisignature model and optional 3-of-5 expansion
- Governance authorization separate from keyholder transaction execution
- Annual Community Reserve Roundtable and public reporting sequence
- Security policy and public disclaimer
- Official ABR, CBR, legislative, and third-party links
- Illinois legislative record separating adopted HR0446 from proposed SB3743 and HB5621

### Superseded

- Previous 17 BTC target
- Three-BTC emergency allocation
- "Yield begins" terminology
- Five-pillar yield model
- 90% community / 10% operations allocation
- Statement that only yield, rather than Reserve Bitcoin, would be used

The superseded items remain visible in Git history for transparency but are not part of the August 2026 framework.
