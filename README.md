# 🌟 Stellar Crowdfunding Platform (Lumina Fund)

<div align="center">

![CI](https://github.com/Lumina-Network/lumina-fund/workflows/CI/badge.svg)
![Security](https://github.com/Lumina-Network/lumina-fund/workflows/Security%20Scan/badge.svg)
![Coverage](https://codecov.io/gh/Lumina-Network/lumina-fund/branch/main/graph/badge.svg)

![Stellar](https://img.shields.io/badge/Stellar-Soroban-7D00FF?style=for-the-badge&logo=stellar)
![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?style=for-the-badge&logo=typescript)
![Rust](https://img.shields.io/badge/Rust-2021-000000?style=for-the-badge&logo=rust)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Coverage](https://img.shields.io/badge/Coverage->80%25-brightgreen?style=for-the-badge)

**A secure, milestone-based decentralized crowdfunding platform built on the Stellar network.**

[Features](#-features) • [Quick Start](#-quick-start) • [User Guides](docs/user-guides/README.md) • [Documentation](#-documentation) • [Contributing](#-contributing) • [Roadmap](#-roadmap)

</div>

---

## 📑 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [Smart Contracts](#-smart-contracts)
- [Frontend Application](#-frontend-application)
- [Testing](#-testing)
- [CI/CD](#-cicd)
- [Deployment](#-deployment)
- [Configuration](#-configuration)
- [Contributing](#-contributing)
- [Roadmap](#-roadmap)
- [FAQ](#-faq)
- [License](#-license)

---

## 🎯 Overview

**Lumina Fund** is a decentralized application that enables entrepreneurs, creators, and NGOs to raise capital transparently on the Stellar blockchain. By leveraging smart contracts, Lumina ensures that funds are released based on predefined milestones, protecting backers and ensuring accountability.

### Why Lumina Fund?

- **🔒 Milestone Escrow**: Funds are locked in a smart contract and released only when backers approve milestones.
- **💸 Low Fees**: Leverage Stellar's ultra-low transaction costs for micropayments and donations.
- **🌍 Global Reach**: Borderless fundraising accessible to anyone with an internet connection.
- **🤝 Trustless**: Non-custodial architecture means the platform never holds your funds.
- **📈 Real-time Tracking**: On-chain transparency for all raised funds and expenditures.

---

## ✨ Features

### Current Features (MVP)

#### 🏦 Campaign Smart Contract
- ✅ Create funding campaigns with strict deadlines and funding goals.
- ✅ Support for XLM and custom Stellar assets (USDC, EURC).
- ✅ Milestone-based fund unlocking.
- ✅ Automated refunds if funding goals are not met.
- ✅ Backer voting power proportional to contribution size.

#### 🎨 Frontend Application
- ✅ Wallet connection via Freighter & Albedo.
- ✅ Campaign discovery dashboard.
- ✅ Interactive campaign creation wizard.
- ✅ Mobile-first and responsive design.
- ✅ Real-time progress bars and funding metrics.

#### 🖼️ Campaign Media
- ✅ Decentralized storage of campaign assets (images, pitch decks) via IPFS.
- ✅ On-chain metadata referencing IPFS CIDs.

#### 🧪 Testing & Quality
- ✅ Comprehensive unit tests for Rust contracts.
- ✅ E2E testing for the React frontend.
- ✅ Property-based testing for voting mechanics.

---

## 🏗️ Architecture

### System Overview

```text
┌─────────────────────────────────────────────────────────────┐
│                    Frontend (React/TS)                       │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │   Campaign   │  │   Backer     │  │  Milestone   │     │
│  │  Dashboard   │  │   Gateway    │  │   Voting     │     │
│  └──────────────┘  └──────────────┘  └──────────────┘     │
└─────────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                  Stellar Network (Soroban)                   │
│  ┌──────────────────────────────────────────────────────┐   │
│  │          Crowdfund Contract (Rust)                   │   │
│  │  - create_campaign()                                 │   │
│  │  - pledge_funds()                                    │   │
│  │  - vote_milestone()                                  │   │
│  │  - claim_funds() / refund()                          │   │
│  └──────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

### Smart Contracts
| Technology | Version | Purpose |
|------------|---------|---------|
| **Rust** | 2021 | Smart contract programming |
| **Soroban SDK** | 21.0.0 | Stellar smart contract framework |
| **proptest** | 1.4 | Property-based testing |

### Frontend
| Technology | Version | Purpose |
|------------|---------|---------|
| **React** | 19.2.0 | UI framework |
| **TypeScript** | 5.9.3 | Type safety |
| **Vite** | 8.0.0-beta | Build tool |
| **Tailwind CSS** | 4.1.18 | Styling framework |

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** 18+
- **Rust** 1.70+ with `wasm32-unknown-unknown` target
- **Soroban CLI**
- **Freighter Wallet**

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/Lumina-Network/lumina-fund.git
cd lumina-fund
```

2. **Install frontend dependencies**
```bash
cd frontend
npm install
```

3. **Build the smart contract**
```bash
cd ../contracts/crowdfund
cargo build --target wasm32-unknown-unknown --release
```

---

## 📁 Project Structure

```text
lumina-fund/
├── contracts/                   # Smart contracts
│   ├── crowdfund/               # Campaign logic
│   │   ├── src/
│   │   │   ├── lib.rs           # Main contract logic
│   │   │   ├── storage.rs       # State management
│   │   │   └── types.rs         # Custom structs and enums
│   │   └── Cargo.toml
├── frontend/                    # React frontend
│   ├── src/
│   │   ├── components/          # UI Elements
│   │   ├── hooks/               # Custom Soroban hooks
│   │   └── services/            # API and Wallet integrations
├── scripts/                     # Deployment scripts
└── README.md
```

---

## 📜 Smart Contracts

### Crowdfund Contract

#### Core Functions

##### `create_campaign`
Initializes a new campaign with a specific funding goal and deadline.
```rust
pub fn create_campaign(
    env: Env,
    creator: Address,
    title: String,
    target_amount: i128,
    deadline: u64,
    token: Address,
) -> Address
```

##### `pledge_funds`
Allows users to contribute tokens to an active campaign.
```rust
pub fn pledge_funds(
    env: Env,
    backer: Address,
    campaign_id: Address,
    amount: i128,
) -> Result<(), Error>
```

##### `claim_funds`
Callable by the creator if the funding goal is reached and deadlines/milestones are met.
```rust
pub fn claim_funds(
    env: Env,
    creator: Address,
    campaign_id: Address,
) -> Result<(), Error>
```

---

## 🤝 Contributing
Please see our [Contributing Guidelines](CONTRIBUTING.md) for details. We welcome PRs for new features, bug fixes, and documentation improvements!

## 🗺️ Roadmap
- **Q2 2026**: Mainnet MVP Launch & Code Audit
- **Q3 2026**: Integration with fiat on-ramps
- **Q4 2026**: Multi-signature campaign management
- **Q1 2027**: Lumina DAO for decentralized platform governance

## 📄 License
This project is licensed under the MIT License.
