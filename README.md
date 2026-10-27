# ChoiceMarket

**An on-chain prediction market in development.**

ChoiceMarket is an independent project exploring how different expectations about future events can be expressed through market prices.

Prediction markets use economic incentives to express expectations rather than opinions alone. ChoiceMarket is developing the technical foundations for this mechanism across different subjects.

> **Notice — Development and testnet only**
>
> ChoiceMarket does **not** currently offer public real-money trading, accept customer deposits, or operate a public wagering or investment service. Protocol testing described here uses testnet tokens with **no monetary value**.
>
> Nothing in this repository is an offer, solicitation, investment advice, or invitation to trade or wager in any jurisdiction.

## What We're Building

- **YES/NO markets:** Protocol-accounted YES/NO positions can be bought and sold through a Fixed Product Market Maker (FPMM). Initial V1 positions are **not freely transferable between wallets**.
- **On-chain financial execution:** Smart contracts govern trade execution, collateral-backed ownership, and settlement.
- **User-authorized transactions:** The application includes embedded-wallet access and selected external-wallet configurations **under testing**. Supported sponsored flows use Safe-based smart accounts.
- **Bounded gas sponsorship:** Eligible testnet transactions can be submitted with sponsored gas. Users still authorize financial actions.
- **Result determination and redemption:** Results are proposed and reviewed by designated roles under on-chain rules. Eligible positions are redeemable according to finalized outcomes.

## Development Status

ChoiceMarket is in active development and testing on **Base Sepolia**, the test network of the Base Ethereum Layer 2.

Financial contracts, position accounting, consumer Market flows, wallet integration, sponsored execution, and settlement have been implemented. One controlled end-to-end test completed successfully with an embedded-wallet account and a selected third-party mobile wallet configuration. Other repeat tests exposed reliability issues, and further validation remains necessary.

**ChoiceMarket is not a live public or real-money prediction-market trading platform.**

Implementation, success in one controlled test, repeat-run reliability, independent security assurance, and production readiness are different milestones. See [Development Status](DEVELOPMENT_STATUS.md).

## Technical Documentation

- [Architecture Overview](ARCHITECTURE.md) — Components, financial responsibilities, operator authority, and trust boundaries.
- [Development Status](DEVELOPMENT_STATUS.md) — Implemented capabilities, selected test milestones, and unresolved limitations.

The main application and protocol source code remain in a separate private development repository.

**This is a public-facing documentation repository, not an open-source release of the ChoiceMarket application.**

## Safety and Official Communications

ChoiceMarket has **not announced any ChoiceMarket-issued token, airdrop, or public trading application**. We will never ask for your wallet recovery phrase, seed phrase, or private keys. Treat purported ChoiceMarket trading, claim, reward, or deposit requests as unverified.

ChoiceMarket is independent and is **not affiliated with or endorsed by Base, Coinbase, Safe, or any wallet provider**.
