# FractProp — Decentralized Fractional Real Estate Platform

- **Team Name:** SoftSuite Technologies
- **Payment Details:**
  - **DOT**: 15i7oq5f9M2H1bZCQR5pApX1bVRUQbkPVvStqgTKtMsyWLiC
  - **Payment**: 15i7oq5f9M2H1bZCQR5pApX1bVRUQbkPVvStqgTKtMsyWLiC (USDC)
- **Level:** 3

---

## Project Overview :page_facing_up:

### Overview

- **Tagline:** Democratizing real estate investment through blockchain-powered fractional ownership on Polkadot.

- **Description:** FractProp is a decentralized platform that enables anyone to invest in real estate by purchasing fractional tokenized shares of properties. By lowering the minimum investment barrier from tens of thousands of dollars to as little as $10, FractProp opens one of the world's most stable asset classes to everyday investors globally. The platform handles property tokenization, KYC-compliant investor onboarding, fractional trading, and automated rental yield distribution — all on-chain.

- **Polkadot/Substrate Integration:** FractProp leverages Polkadot's ecosystem in the following ways:
  - **ink! smart contracts** deployed on a Substrate-based chain for property tokenization (PSP-22/PSP-34 compliant security tokens)
  - **XCM (Cross-Consensus Messaging)** for cross-chain asset transfers between Polkadot parachains
  - **Substrate pallets** for custom real estate ownership logic, yield distribution, and compliance enforcement
  - **Polkadot AssetHub** for minting and managing real estate security tokens
  - Multi-chain bridge connecting Polkadot with Ethereum and BSC ecosystems

- **Why we are building this:** Real estate is a $326 trillion global asset class, yet it remains inaccessible to the majority of the world's population due to high capital requirements, geographic restrictions, and lack of liquidity. Our team at SoftSuite Technologies has 8+ years of experience building fintech and blockchain solutions for clients across Pakistan, UAE, UK, and Denmark. We identified a critical gap: no Polkadot-native platform exists for compliant, fractional real estate investment. FractProp fills this gap by bringing institutional-grade real estate tokenization to the Polkadot ecosystem.

---

### Project Details

**UI Mockups / Prior Work:**
- MVP is already built and live at [fractprop.com](https://fractprop.com)
- React.js frontend with property listing, investor dashboard, and portfolio tracking
- Laravel REST API backend with PostgreSQL database

**Core Architecture:**

```
┌─────────────────────────────────────────────────┐
│                  FractProp Platform              │
├──────────────┬──────────────┬───────────────────┤
│  React/Next  │  Laravel API │  Node Microsvcs   │
│  Frontend    │  Backend     │  (notifications,  │
│              │              │   yield engine)   │
├──────────────┴──────────────┴───────────────────┤
│              Substrate / ink! Layer              │
│  - Property Token Pallet (PSP-22 security token)│
│  - Yield Distribution Pallet                    │
│  - Governance/Voting Pallet                     │
│  - KYC Registry Pallet                          │
├─────────────────────────────────────────────────┤
│         Multi-Chain Bridge Layer                │
│    Polkadot ↔ Ethereum ↔ BSC via XCM/bridge    │
└─────────────────────────────────────────────────┘
```

**Technology Stack:**
| Layer | Technology |
|---|---|
| Frontend | React.js, Next.js, TailwindCSS |
| Backend | Laravel (PHP), Node.js microservices |
| Blockchain | Substrate, ink! smart contracts, Solidity |
| KYC/AML | DIDIT KYC integration |
| Database | PostgreSQL, Redis |
| DevOps | Docker, GitHub Actions CI/CD |
| Wallet | Polkadot.js, MetaMask (multi-chain) |

**Data Models — Core API Specifications:**

*Property Token (PSP-22 compliant):*
```rust
pub struct PropertyToken {
    property_id: u64,
    total_supply: Balance,       // Total fractional shares
    price_per_share: Balance,    // USD value per fraction
    yield_rate: Perbill,         // Annual rental yield %
    kyc_required: bool,
    owner: AccountId,
    metadata_uri: Vec<u8>,       // IPFS property documents
}
```

*Investor KYC Registry:*
```rust
pub struct KycRecord {
    account: AccountId,
    status: KycStatus,           // Pending / Approved / Rejected
    country: CountryCode,
    verification_hash: Hash,     // Off-chain verification proof
    expiry: BlockNumber,
}
```

**What FractProp will NOT provide:**
- It is not a real estate agency or property management company
- It does not handle physical property maintenance
- It is not a lending/mortgage platform
- Deployment, hosting, and marketing costs are excluded from this grant

---

### Ecosystem Fit

- **Where it fits:** FractProp is a DeFi/RWA (Real World Assets) application built on Polkadot. It bridges traditional real estate with decentralized finance, fitting squarely within the growing RWA narrative in the Polkadot ecosystem alongside projects like Centrifuge (on Ethereum) but natively on Polkadot.

- **Target Audience:**
  - Retail investors seeking low-barrier real estate exposure
  - Real estate developers seeking liquidity via tokenization
  - DeFi users looking to diversify into real-world assets
  - Polkadot parachain teams building RWA infrastructure

- **Needs addressed:**
  - Liquidity in an otherwise illiquid asset class
  - Global access to real estate investment regardless of geography
  - Transparent, on-chain ownership and yield distribution
  - Compliance-first architecture meeting regulatory requirements

- **Evidence of need:**
  - The global real estate tokenization market is projected to reach $1.4 trillion by 2026 (World Economic Forum)
  - 64% of millennials cite high capital requirements as the primary barrier to real estate investment (Deloitte, 2023)
  - Polkadot currently has no dedicated, production-ready fractional real estate platform

- **Similar projects:**
  - *Centrifuge* (Ethereum/Polkadot bridge) — focuses on invoice financing, not real estate
  - *RealT* (Ethereum) — US-only, no cross-chain support, no Polkadot integration
  - *Lofty.ai* (Algorand) — limited to US properties, single-chain
  - **FractProp differentiates** through: native Polkadot/Substrate architecture, multi-chain support via XCM, Pakistan/emerging market focus, and DIDIT KYC compliance layer

---

## Team :busts_in_silhouette:

### Team Members

- **Ahmad** (Team Lead & Blockchain Architect)
- SoftSuite Technologies Development Team (13 members — frontend, backend, blockchain, mobile)

### Contact

- **Contact Name:** Ahmad Shahzaib
- **Contact Email:** ahmed.shahzaib.789@gmail.com
- **Website:** https://fractprop.com | https://softsuitetech.com

### Legal Structure

- **Registered Address:** Building # 71, Galaxy Town, Bosan Rd, Gulgasht Colony, Multan, 60000, Pakistan
- **Registered Legal Entity:** SoftSuite Technologies

### Team's Experience

**Ahmad — Founder & Lead Developer:**
- 8+ years of full-stack and blockchain development
- 300+ completed projects across fintech, proptech, and Web3
- Expertise: Laravel, React, React Native, Solidity, Rust, Node.js, Web3
- Top Rated Plus on Upwork with 5.0 rating across 200+ contracts
- Previously built:
  - **ProlificEx** — P2P cryptocurrency marketplace with multi-chain wallet and escrow smart contracts
  - **Rift** — Multi-chain DeFi platform with cross-chain smart contracts
  - **Pet Social App** — React Native/Expo app with microservices backend, Firebase, DIDIT KYC
  - **WhiteboardAI** — SaaS platform with ElevenLabs, Stripe, AWS integration
  - Multiple enterprise ERP/CRM systems for international clients (UK, UAE, Denmark, Pakistan)

**Team capabilities:**
- Substrate/ink! smart contract development
- Cross-chain bridge architecture
- KYC/AML compliance systems
- React/Next.js frontend development
- Laravel/Node.js backend APIs
- Mobile development (React Native/Expo)

### Team Code Repos

- https://github.com/Ahmad-Shahzaib
- https://github.com/Ahmad-Shahzaib/fractprop *(add if repo exists)*

Team member GitHub accounts:
- https://github.com/Ahmad-Shahzaib

### Team LinkedIn Profiles

- https://www.linkedin.com/in/ahmad-shahzaib-tech-lead/

---

## Development Status :open_book:

- **Live MVP:** [fractprop.com](https://fractprop.com) — React frontend with property listings, investor dashboard, and portfolio tracking built on Laravel backend
- **Prior research:** SECP (Securities and Exchange Commission of Pakistan) regulatory sandbox research conducted for compliant token issuance framework
- **Tech foundation:** DIDIT KYC integration already implemented and tested in production (Pet Social App project)
- **Smart contract research:** Reviewed PSP-22 (Polkadot ink! fungible token standard) and ERC-1400 security token standards for compliance architecture
- **RWA landscape analysis:** Studied Centrifuge, RealT, and Lofty.ai architectures to identify gaps in the Polkadot ecosystem

---

## Development Roadmap :nut_and_bolt:

### Overview

- **Total Estimated Duration:** 6 months
- **Full-Time Equivalent (FTE):** 4 FTE
- **Total Costs:** 100,000 USD
- **DOT %:** 50% DOT / 50% USDC

---

### Milestone 1 — Substrate Pallets & ink! Smart Contracts for Property Tokenization

- **Estimated Duration:** 6 weeks
- **FTE:** 4
- **Costs:** 25,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License | Apache 2.0 |
| **0b.** | Documentation | Inline code documentation + tutorial on deploying property token pallet on local Substrate node and minting test property tokens |
| **0c.** | Testing and Testing Guide | Unit tests covering token minting, transfer, burn, and access control. Guide on running tests with `cargo test` |
| **0d.** | Docker | Dockerfile for spinning up local Substrate node with FractProp pallets pre-installed |
| 1. | Substrate Pallet: Property Registry | Custom pallet for registering real estate properties on-chain with metadata (IPFS documents, valuation, location) |
| 2. | ink! Smart Contract: PropertyToken (PSP-22) | PSP-22 compliant security token contract representing fractional shares of a registered property |
| 3. | ink! Smart Contract: TokenFactory | Factory contract for deploying new PropertyToken contracts per property listing |
| 4. | Substrate Pallet: KYC Registry | On-chain KYC status registry — stores verification hashes from off-chain DIDIT KYC provider |

---

### Milestone 2 — KYC/AML Compliance Layer & Investor Onboarding

- **Estimated Duration:** 4 weeks
- **FTE:** 3
- **Costs:** 20,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License | Apache 2.0 |
| **0b.** | Documentation | Integration guide for DIDIT KYC + Substrate KYC Registry pallet |
| **0c.** | Testing and Testing Guide | Tests for KYC verification flow, whitelist enforcement on token transfers, and compliance checks |
| **0d.** | Docker | Updated Dockerfile including KYC oracle service |
| 1. | KYC Oracle Service | Node.js off-chain worker that listens to KYC approval events from DIDIT and submits verified proofs to the on-chain KYC Registry pallet |
| 2. | Compliance Middleware | Transfer restriction logic in PropertyToken contract — blocks non-KYC'd addresses from acquiring tokens |
| 3. | Investor Dashboard (React) | Frontend interface for investor KYC onboarding, wallet connection (Polkadot.js), and portfolio overview |

---

### Milestone 3 — Fractional Trading Engine & DEX Integration

- **Estimated Duration:** 6 weeks
- **FTE:** 4
- **Costs:** 25,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License | Apache 2.0 |
| **0b.** | Documentation | Trading engine API docs + guide on listing/buying/selling fractional property shares |
| **0c.** | Testing and Testing Guide | Tests for order matching, yield calculation, and settlement logic |
| **0d.** | Docker | Full platform Docker Compose including trading engine |
| 1. | ink! Smart Contract: Marketplace | Peer-to-peer order book for listing and trading fractional property shares with KYC enforcement |
| 2. | Substrate Pallet: Yield Distribution | Automated rental yield distribution pallet — distributes collected rent proportionally to all token holders per property |
| 3. | Yield Dashboard (React) | Frontend showing yield history, next distribution date, and earnings per property investment |

---

### Milestone 4 — Multi-Chain Bridge (Polkadot ↔ Ethereum ↔ BSC)

- **Estimated Duration:** 6 weeks
- **FTE:** 4
- **Costs:** 20,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License | Apache 2.0 |
| **0b.** | Documentation | XCM bridge integration guide + cross-chain transfer tutorial |
| **0c.** | Testing and Testing Guide | Tests for cross-chain token locking, minting, and redemption flows |
| **0d.** | Docker | Bridge relayer service included in Docker Compose |
| 1. | XCM Integration | XCM message passing for cross-parachain PropertyToken transfers within Polkadot ecosystem |
| 2. | Solidity Bridge Contract | EVM-side bridge contract (Ethereum/BSC) for locking/unlocking wrapped property tokens |
| 3. | Bridge Relayer Service | Node.js off-chain relayer monitoring both chains and relaying cross-chain transfer messages |

---

### Milestone 5 — Audit, Testing, Documentation & Open-Source Release

- **Estimated Duration:** 4 weeks
- **FTE:** 3
- **Costs:** 10,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License | Apache 2.0 |
| **0b.** | Documentation | Complete developer documentation, architecture diagrams, and end-user guides |
| **0c.** | Testing and Testing Guide | End-to-end integration tests covering full user journey from KYC to property investment to yield claim |
| **0d.** | Docker | Final production-ready Docker Compose for full platform deployment |
| **0e.** | Article | Technical article published on Medium/Polkadot forum explaining FractProp architecture, RWA tokenization approach, and how it contributes to the Polkadot ecosystem |
| 1. | Security Audit | Smart contract audit of all ink! contracts and Substrate pallets (third-party auditor) |
| 2. | Open-Source Release | Full codebase published on GitHub under Apache 2.0 license |
| 3. | Testnet Deployment | Full platform deployed on Rococo/Westend testnet with public access |

---

## Future Plans

**Short-term (post-grant):**
- Launch on Polkadot mainnet with 5–10 initial property listings in Pakistan and UAE
- Pursue SECP (Pakistan) regulatory sandbox approval for compliant token issuance
- Integrate additional KYC providers for global investor onboarding
- Mobile app release (React Native) for iOS and Android

**Long-term maintenance & development:**
- Platform sustainability funded through a 1–2% transaction fee on property token trades and a small yield distribution fee
- Expand property listings to UK, Denmark, and UAE markets (existing client relationships)
- Apply for follow-up W3F grant for governance module (DAO-based property management voting)
- Explore becoming a Polkadot parachain as platform volume grows

**Ecosystem contribution:**
- Open-source PSP-22 security token standard implementation will benefit other RWA projects building on Polkadot
- KYC oracle pattern will be reusable by any compliance-requiring dApp in the ecosystem

---

## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?** Email

**Work already done:**
- Live MVP at fractprop.com with React frontend and Laravel backend
- DIDIT KYC integration already implemented in production
- SECP regulatory sandbox research completed
- P2P trading engine experience from ProlificEx cryptocurrency marketplace project
- Multi-chain smart contract experience from Rift DeFi platform project

**No previous W3F grants have been applied for.**
