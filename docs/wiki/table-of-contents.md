# Table of Contents

!!! tip ""
    **This wiki contains a high level technical overview of Mugle.**
    For more details about the implentation, please look at the Mugle documentation on docs.rs

    - mugle: [api](https://docs.rs/mugle_api/latest), [core](https://docs.rs/mugle_core/latest), [chain](https://docs.rs/mugle_chain/latest), [util](https://docs.rs/mugle_util/latest), [store](https://docs.rs/mugle_store/latest), [keychain](https://docs.rs/mugle_keychain/latest), [p2p](https://docs.rs/mugle_p2p/latest), [pool](https://docs.rs/mugle_pool/latest), [config](https://docs.rs/mugle_config/latest), [servers](https://docs.rs/mugle_servers/latest).
    - mugle_wallet: [wallet_api](https://docs.rs/mugle_wallet_api/latest), [wallet](https://docs.rs/mugle_wallet/latest).

## Introduction

- [Mugle for Bitcoiners](introduction/mugle-for-bitcoiners.md) - Explaining Mugle from a Bitcoiner's perspective
- [Mimblewimble](introduction/mimblewimble/mimblewimble.md) - A technical introduction to Mimblewimble </br>
    1. [Elliptic Curves](introduction/mimblewimble/ecc.md)
    1. [Commitments](introduction/mimblewimble/commitments.md)
    1. [Mimblewimble](introduction/mimblewimble/mimblewimble.md)

## Transactions

- [Slates](transactions/slates.md)
- [Slatepack](transactions/slatepack.md)
- [Payment Proofs](transactions/payment-proofs.md)
- [Contracts](transactions/contracts.md)

## Blocks

- [Header](blocks/block-header.md)
- [Body](blocks/block-body.md)
- [Fees & Weight](blocks/fees-and-weight.md)

## Chain State

- [Merkle Mountain Ranges](chain-state/merkle-mountain-range.md)
- [State & Pruning](chain-state/state-and-pruning.md)
- [Chain Sync](chain-state/chain-sync.md)

## Miscellaneous

- [Cuckoo Cycle](miscellaneous/cuckoo-cycle.md)
- [Dandelion](miscellaneous/dandelion.md)
- [Switch Commitments](miscellaneous/switch-commitments.md)
- [Coinbase Maturity Rule](miscellaneous/coinbase-maturity-rule.md)
- [NRD Kernels](miscellaneous/nrd-kernels.md)

## API

- [Node API](api/node-api.md)
- [Wallet API](api/wallet-api.md)
- [Stratum RPC](api/stratum-rpc.md)

## Security Process

- [Mugle's Security Process](security-process/mugle-security-process.md)
- [Security Team](security-process/security-team.md)
- [Code Audits](security-process/code-audits.md)

## Services

- [List of Services](services/list-of-services.md)
- [Slatepack Integration Guide](services/slatepack-integration.md)

## More

- [Resources](resources.md)
