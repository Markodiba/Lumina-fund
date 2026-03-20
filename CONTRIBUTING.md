# Contributing to Lumina Fund

First off, thank you for considering contributing to **Lumina Fund**! We welcome contributions from anyone, whether you're a seasoned Rust developer, a React specialist, or a passionate community member looking to improve documentation.

Below is a breakdown of the types of work you can post and contribute to in this repository.

## 🐛 Bug Fixes
Bugs are an inevitable part of software. If you find a bug, please create an Issue using the "**Bug Report**" template. Types of bugs we commonly track:
- **Smart Contract Vulnerabilities**: Errors in Soroban logic, miscalculations in fee deductions, or edge-case exploits in milestone unlocking. *(Note: If you find a critical security flaw, please do not open a public issue. Email security@lumina.network instead).*
- **Frontend Issues**: Wallet connection drops in Freighter or Albedo, UI glitches, responsive design failures on mobile, or incorrect token balances being displayed.
- **Build Errors**: Issues compiling the Rust contract or starting the Vite frontend server.

## ✨ New Features
Have an idea to make Lumina Fund better? Open a "**Feature Request**" issue! Examples include:
- **Contract Enhancements**: Adding support for batch campaigning, decentralized voting for milestone disputes, or new token integrations (e.g., EURC).
- **Web App Features**: Adding fiat on-ramps (e.g., via integration with Stellar anchors), a new dashboard analytics page, or email notifications for backers.
- **Integrations**: Support for additional Stellar wallets (e.g., xBull) or decentralized storage solutions like Arweave as an alternative to IPFS.

## 📚 Documentation
Documentation is crucial for onboarding new developers and users. We always need help with:
- **README Updates**: Fixing typos, updating the roadmap, or clarifying setup instructions.
- **User Guides**: Writing tutorials on how to create a campaign, how to vote on a milestone, or how to connect a wallet.
- **Code Comments**: Adding standard RustDoc (`///`) documentation to the `crowdfund` smart contract functions.
- **API Specs**: Documenting Soroban RPC integration methods in the frontend.

## 🧪 Testing
A robust DeFi application requires extensive testing. Contributions here are highly valued:
- **Smart Contract Tests**: Writing unit tests for specific `lib.rs` endpoints. Expanding our **property-based tests** using the `proptest` crate to ensure edge cases are covered.
- **Frontend Tests**: Enhancing our Vite/React test suites, adding integration tests for the campaign creation wizard, or writing end-to-end tests.

## 🧹 Tooling, Chores & Refactoring
Sometimes the most impactful work is just keeping the house clean:
- **Dependency Updates**: Bumping React, Soroban SDK, or Tailwind versions, and ensuring the app still builds.
- **Refactoring**: Cleaning up complex React hooks or optimizing Rust WASM compilation size.
- **CI/CD**: Improving GitHub Actions workflows to be faster or to run additional security scans like `cargo audit`.

## How to Submit Your Work
1. **Fork** the repository and create your branch from `main`.
2. Ensure you have tested your code locally using `npm test` or `cargo test`.
3. If you changed APIs or components, update the documentation.
4. Open a **Pull Request (PR)** with a clear title and description referencing any related issues.

We look forward to building a borderless crowdfunding ecosystem with you!
