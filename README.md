# Moony Deployment

[![Moony](https://img.shields.io/badge/Moony-Deployment-blue)](https://moonylabs.com)
[![Go](https://img.shields.io/badge/Go-1.21+-00ADD8?logo=go)](https://go.dev/)
[![License](https://img.shields.io/badge/license-MIT-lightgrey.svg?style=flat)](LICENSE.md)

This repository contains the Open Code Protocol (OCP) server codebase that was used to deploy Moony on the Solana blockchain. Moony was deployed by Moony Labs, LLC. using infrastructure developed by Flipcash Inc.

## About Moony

[Moony](https://moonylabs.com) is a decentralized digital asset deployed on the Solana blockchain, designed to facilitate permissionless transactions without intermediaries. All issuance is governed by an immutable smart contract that eliminates discretionary control and enables open participation in internet capital markets.

- **Fixed Supply:** 21,000,000 tokens, all pre-minted during contract initialization
- **Proof of Liquidity:** Tokens are unlocked through USDF deposits, with all capital retained as on-chain liquidity
- **Bonding Curve:** Deterministic pricing mechanism that increases cost as more tokens are unlocked
- **Permissionless:** Anyone can unlock or redeem Moony directly through the Reserve Contract

**Learn more:** [Documentation](https://moonylabs.com/docs) | [Website](https://moonylabs.com)

## Repository Purpose

This repository mirrors the [Open Code Protocol (OCP) server](https://github.com/code-payments/ocp-server) codebase maintained by Flipcash Inc. The OCP server provides the infrastructure for deploying currencies on Solana, and this codebase was used to deploy Moony's Reserve Contract and related infrastructure.

The repository serves as:
- **Attribution** - Reference to the OCP server codebase that enabled Moony's deployment
- **Transparency** - Open access to the infrastructure code used for Moony
- **Testing** - Currently configured for testing using "Jeffy" addresses

**Note:** Moony operates as an immutable smart contract on Solana. This repository contains the deployment infrastructure code, not the operational code for running Moony (which is entirely on-chain).

## What is the Open Code Protocol?

The Open Code Protocol (OCP) is a next-generation currency launchpad and payment system built on Solana. It provides the first L2 solution on top of Solana, utilizing an intent-based system backed by a sequencer to handle transactions.

The OCP server is a monolith containing gRPC/web services and workers that power currency deployment, payment processing, and transaction sequencing. Flipcash Inc. developed this infrastructure, which Moony Labs used to deploy Moony as an independent protocol.

## Project Structure

```
.
├── ocp/              # Open Code Protocol core implementation
│   ├── rpc/         # gRPC and web service implementations
│   ├── worker/      # Background workers (currency, sequencer, etc.)
│   └── config/      # Configuration management
├── config/           # Application configuration
├── grpc/             # gRPC server setup
└── currency/         # Currency-specific utilities
```

## APIs

The gRPC APIs provided by the Open Code Protocol server can be found in the [ocp-protobuf-api](https://github.com/code-payments/ocp-protobuf-api) project.

## Contributing

This repository mirrors the upstream OCP server. For contributions to the core OCP server codebase, please contribute to the [upstream repository](https://github.com/code-payments/ocp-server).

For Moony-specific documentation or attribution improvements, contributions are welcome through pull requests.

## Upstream

This repository is synced from the upstream [code-payments/ocp-server](https://github.com/code-payments/ocp-server) repository. The commit history reflects the upstream development, ensuring this repository accurately represents the OCP server codebase that was used for Moony's deployment.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

---

**Moony Labs** | [Website](https://moonylabs.com) | [Documentation](https://moonylabs.com/docs) | [GitHub](https://github.com/moonylabs)
