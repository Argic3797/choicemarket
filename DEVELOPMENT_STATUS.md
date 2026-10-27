# ChoiceMarket — Development Status

**Stage:** Active development / controlled testnet validation  
**Primary integration-test network:** Base Sepolia  
**Last updated:** October 27, 2026  
**Public real-money trading:** Not available  
**Production readiness:** Not established

ChoiceMarket has progressed beyond a concept or static interface prototype. Financial smart contracts, a consumer application, wallet-access paths, gas-sponsored transactions, and outcome-resolution/settlement mechanisms have been implemented.

This document distinguishes **implemented**, **tested in a particular controlled configuration**, **requiring further repeatability testing**, and **not established for production**.

## 1. Implemented Capabilities

### Financial Engine and Positions

- Binary YES/NO markets using a Fixed Product Market Maker (FPMM).
- On-chain BUY/SELL execution and cost-basis accounting.
- Collateral-backed, protocol-accounted outcome positions that are not freely transferable between wallets.
- Liquidity accounting and version-pinned Market terms.

### Consumer Application

- Event/Market data models and a Market catalog checked against on-chain state.
- Market discovery, trading, positions, resolution status, and redemption interfaces.
- Wallet-access handling and consumer transaction-state presentation.

### Wallet and Gas Sponsorship

- Embedded-wallet access and selected external-wallet configurations under testing.
- Safe-based smart accounts in supported consumer execution paths.
- Bounded gas sponsorship for user-authorized transactions.

Supported gas sponsorship does not eliminate user authorization or establish universal wallet compatibility.

### Resolution, Operator Roles, and Evidence

- On-chain Market closing, result proposal/challenge/review, and finalization.
- YES/NO/INVALID financial outcomes and redemption.
- Designated operator-controlled roles for parts of resolution, closure, and pausing; production governance remains undecided.
- Off-chain evidence records and consumer-facing resolution information.

## 2. Selected Completed Validation Milestones

**Financial contract validation**

Core financial functionality has been exercised through automated/integration tests and comparisons with reference calculations.

**Sponsored execution**

A controlled Base Sepolia rehearsal successfully exercised sponsored Safe-based transactions through trading and redemption while the consumer Safe held no native gas token.

**Full controlled V2 test lifecycle — October 2026**

One controlled Base Sepolia V2 test instance completed its entire planned execution sequence for an embedded-wallet account and **one third-party mobile-wallet configuration**. The tested lifecycle included sponsored Safe deployment, trade authorization, BUY/SELL operations, Market close, unchallenged result processing, finalization, and redemption/Claim through both wallet paths.

This is a **successful test of those specific configurations**, not evidence that every external wallet works or that repeated executions will always succeed.

**Consumer integration**

Market discovery, trading, position management, and resolution presentation are integrated into the application.

## 3. Repeat Testing and Known Limitations

Later controlled repeat instances in October 2026 stopped before completing their planned lifecycles after operational issues. Corresponding code corrections were merged, but a merged correction is **not itself evidence of a successful subsequent complete repeat run**.

As of this document's last update, repeat-run reliability and broader wallet-configuration coverage have **not been established**.

Ongoing validation priorities include:

- Additional full lifecycle rehearsals and confirmation of repeatability.
- External-wallet authentication and transaction signing across more configurations.
- Sponsored transaction admission, consistency, failure handling, and recovery.
- Additional Market lifecycle, finalization, and redemption scenarios.
- Real external-user feedback and usability testing.

**Resolution evidence availability:** The underlying off-chain resolution evidence for the completed controlled V2 test was not published as a public evidence record. Its public availability was therefore not validated. On-chain settlement success is distinct from public access to the underlying off-chain source material.

## 4. Not Yet Established

- Production deployment authorization or public real-money trading.
- Broad independent external-user usability validation.
- Comprehensive production security assurance, including any claim of a completed independent production security audit.
- Final production operational controls, role custody, governance, and monitoring.
- Production-scale economic and reliability performance.
- A committed public launch date.

This document is **not an external security audit report** or a legal compliance certification.

## 5. Priorities Before Broader Release

1. Complete additional controlled end-to-end tests and verify repeatability.
2. Independently review important fixes and supporting evidence.
3. Resolve production security, operational-role, and governance requirements.
4. Address applicable legal and launch requirements.
5. Obtain real-user evidence before broader usability or readiness claims.

These priorities are not a launch schedule.

## 6. Documentation and Source Availability

The main application and protocol source remain in a separate private repository. This proposed public-facing repository is an overview of the project's purpose, architecture, and current development status; it is **not an open-source release**.

This status must be checked against actual implementation and execution evidence before publication and updated after material changes.

## Notice — No Public Trading Offer

**ChoiceMarket does not offer real-money trading, accept customer deposits, or operate a public wagering or investment service.** All protocol testing described here uses testnet tokens with **no monetary value**.

Nothing in this documentation is an offer, solicitation, investment advice, or invitation to trade or wager in any jurisdiction.

No ChoiceMarket-issued project token or airdrop has been announced or offered through this documentation. Never disclose your seed phrase, recovery phrase, or private keys to anyone claiming to represent ChoiceMarket.

ChoiceMarket is independent and is not affiliated with or endorsed by Base, Coinbase, Safe, or any wallet provider.
