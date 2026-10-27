# ChoiceMarket — Architecture Overview

ChoiceMarket is an on-chain prediction market in development, currently tested on Base Sepolia.

This document explains the architecture and responsibility boundaries at a high level. It intentionally excludes privileged operational details, addresses, deployment configuration, secrets, and recovery procedures.

## 1. Design Principles

- **On-chain financial authority:** Smart contracts govern collateral, financial positions, Market state, and finalized settlement.
- **Clear separation:** Application databases, community content, and evidence services are not authoritative financial ledgers.
- **User-authorized execution:** Gas sponsorship should not give a transaction submitter independent authority to trade or move user assets.
- **Version-pinned rules:** A LIVE Market's fundamental financial terms should not silently change.
- **Portability:** Core financial semantics are designed for EVM portability; production compatibility across multiple networks has not been established.

## 2. High-Level Components

### Consumer Application

The web interface presents Event/Market discovery, YES/NO trading, positions, and redemption. An Event may group multiple independent binary Markets without combining their financial obligations.

Displayed values may be derived or cached for presentation. Financial actions use current authoritative Market state.

### Wallet Access and Smart Accounts

The application implements an embedded-wallet path and selected external-wallet integration paths in controlled testing. Safe-based smart accounts support sponsored execution in specific configurations.

A consumer must authorize each financial action. Results from one wallet configuration do not establish compatibility across all wallets or settings.

### Bounded Gas Sponsorship

A supporting service may pay gas for eligible consumer-authorized operations, subject to operational restrictions. Sponsorship is conditional and is not a guarantee of unlimited execution.

**Paying gas does not confer independent authority over user assets.**

### On-Chain Financial Contracts

The initial binary trading engine uses an FPMM.

- **Market Registry:** Recognizes Markets and enforces applicable registration, version, and lifecycle boundaries.
- **Position Vault:** Maintains collateral-backed YES/NO outcome ownership and redemption. Initial V1 positions are not freely transferable wallet to wallet.
- **FPMM Market:** Executes BUY/SELL operations and manages Market reserves and liquidity accounting.
- **Resolution Adapter:** Enforces on-chain procedures for outcome proposals, challenges, review, and result determination.

### Operator Authority and Trust Assumptions

**Result proposal, review, and final-review decisions, as well as administrative actions such as closing Markets and pausing trading, involve designated accounts with defined powers.** In current test deployments, those operational roles are exercised by the project. Production role allocation, custody, and governance arrangements remain undecided.

These powers are constrained by on-chain rules, but their existence means ChoiceMarket must **not** be described as having fully decentralized or permissionless outcome determination.

Administrative powers and user asset ownership are distinct responsibilities; the system's trust model does not treat every administrative role as the owner of user funds.

### Resolution Evidence

Off-chain evidence records support transparency and review. They are distinct from the on-chain resolution process and final financial settlement. Storing an evidence record does not, by itself, demonstrate that the underlying evidence is independently or publicly accessible for a particular test.

## 3. Market Lifecycle

1. **Preparation:** Market terms and financial configuration are established.
2. **LIVE:** Eligible YES/NO trading can occur.
3. **CLOSED:** Trading has ended; the financial outcome is not yet final.
4. **Resolution processing:** A result is proposed and may be challenged or reviewed according to applicable rules and designated authorities.
5. **FINALIZED:** An authoritative YES, NO, or INVALID result determines settlement.
6. **Redemption:** Eligible positions can be redeemed according to the finalized outcome.

A LIVE Market's financial terms are version-pinned. CLOSED and FINALIZED are distinct states.

## 4. On-Chain and Off-Chain Responsibilities

**On-chain:** Market financial configuration and state, collateral backing, outcome ownership, trading, liquidity accounting, resolution rules, finalized payout, and redemption.

**Off-chain:** Market discovery and presentation, community and editorial data, evidence records, and derived analytics.

An off-chain record is not a substitute for on-chain financial authority.

## 5. Development Validation and Limits

The project uses financial reference calculations, automated tests, controlled rehearsals, and Base Sepolia execution.

These results establish only the behaviors tested in their respective environments. They do not establish complete wallet compatibility, independent security assurance, production-scale reliability, or regulatory readiness.

See [Development Status](DEVELOPMENT_STATUS.md).

## 6. Scope of This Repository

This is a documentation overview, not an open-source release of the application or a comprehensive security audit. The application source and operational infrastructure materials remain private.

ChoiceMarket is independent and is not affiliated with or endorsed by Base, Coinbase, Safe, or any wallet provider.
