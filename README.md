# Moony Deployment Infrastructure

[![Moony](https://img.shields.io/badge/Moony-Deployment-blue)](https://moonylabs.com)
[![Go](https://img.shields.io/badge/Go-1.21+-00ADD8?logo=go)](https://go.dev/)
[![License](https://img.shields.io/badge/license-MIT-lightgrey.svg?style=flat)](LICENSE.md)

**Moony's production deployment infrastructure** powered by the Open Code Protocol (OCP) server. This repository contains the codebase, configurations, and deployment tooling used to operate Moony on the Solana blockchain.

## About Moony

[Moony](https://moonylabs.com) is a decentralized digital asset deployed on the Solana blockchain, designed to facilitate permissionless transactions without intermediaries. All issuance is governed by an immutable smart contract that eliminates discretionary control and enables open participation in internet capital markets.

- **Fixed Supply:** 21,000,000 tokens, all pre-minted during contract initialization
- **Proof of Liquidity:** Tokens are unlocked through USDF deposits, with all capital retained as on-chain liquidity
- **Bonding Curve:** Deterministic pricing mechanism that increases cost as more tokens are unlocked
- **Permissionless:** Anyone can unlock or redeem Moony directly through the Reserve Contract

**Learn more:** [Documentation](https://moonylabs.com/docs) | [Website](https://moonylabs.com)

## What This Repository Contains

This repository houses **Moony's deployment infrastructure**, including:

- **OCP Server Implementation** - The Open Code Protocol server codebase that powers Moony's currency deployment, payment processing, and transaction sequencing
- **Moony-Specific Configurations** - Deployment settings, contract addresses, and infrastructure configurations for Moony
- **Deployment Tooling** - Scripts, workflows, and automation for managing Moony's on-chain infrastructure
- **Testing Infrastructure** - Test configurations and validation tools for Moony deployments

**Current Status:** This repository is configured for testing using "Jeffy" addresses. Production deployments will use the official Moony contract addresses.

## Deployment Architecture

Moony leverages the Open Code Protocol (OCP), a next-generation currency launchpad and payment system built on Solana. OCP provides the first L2 solution on top of Solana, utilizing an intent-based system backed by a sequencer to handle transactions.

The deployment infrastructure includes:

- **gRPC/Web Services** - API endpoints for currency operations, payments, and account management
- **Transaction Sequencer** - Handles transaction ordering and processing
- **Currency Workers** - Background services managing token issuance, reserves, and redemptions
- **Account Management** - User account creation and key management systems

## Quick Start

### Prerequisites

1. **Install Go 1.21+** - See the [official documentation](https://go.dev/doc/install)
2. **Solana CLI** - Required for on-chain interactions (see [Solana docs](https://docs.solana.com/cli/install-solana-cli-tools))

### Setup

```bash
# Clone the repository
git clone https://github.com/moonylabs/moony-deployment-test.git
cd moony-deployment-test

# Install dependencies
go mod download

# Run tests
make test
```

### Configuration

Configure your deployment by setting environment variables or modifying configuration files in the `config/` directory. See the [OCP documentation](https://github.com/code-payments/ocp-server) for detailed configuration options.

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

Key packages for Moony deployment:
- `ocp/rpc/` - API services for Moony operations
- `ocp/worker/currency/` - Currency deployment and reserve management
- `ocp/worker/sequencer/` - Transaction sequencing
- `ocp/config/` - Moony-specific configuration

## APIs

The gRPC APIs used by Moony are defined in the [ocp-protobuf-api](https://github.com/code-payments/ocp-protobuf-api) project. These APIs handle:

- Currency deployment and configuration
- Payment processing and intent management
- Account creation and key management
- Transaction submission and status

## Moony Deployment Workflow

1. **Configuration** - Set up Moony contract addresses, network settings, and service endpoints
2. **Deployment** - Deploy the OCP server infrastructure for Moony
3. **Currency Setup** - Configure Moony token parameters (supply, bonding curve, reserve contract)
4. **Service Startup** - Launch gRPC services, workers, and sequencer
5. **Monitoring** - Track deployment health, transaction processing, and reserve status

## Contributing

This repository contains Moony's deployment infrastructure. For contributions:

- **Moony-Specific Changes** - Submit pull requests for Moony deployment configurations, documentation, or tooling improvements
- **OCP Server Improvements** - For changes to the core OCP server codebase, please contribute to the [upstream repository](https://github.com/code-payments/ocp-server)

## Codebase Source

This repository is based on the [Open Code Protocol server](https://github.com/code-payments/ocp-server) and is maintained by Moony Labs for Moony's deployment needs. The codebase is periodically synced with upstream improvements while maintaining Moony-specific customizations and configurations.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

---

**Moony Labs** | [Website](https://moonylabs.com) | [Documentation](https://moonylabs.com/docs) | [GitHub](https://github.com/moonylabs)
