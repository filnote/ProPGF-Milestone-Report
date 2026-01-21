# FilNote FEVM

FilNote is a **FIL-denominated credit issuance infrastructure** built on **Filecoin EVM (FEVM)**, enabling Storage Providers (SPs) to issue debt notes backed by real cashflow, and allowing investors to participate through a non-custodial, legally anchored workflow.

The system supports:
- On-chain asset lifecycle management
- Legal document anchoring via IPFS + on-chain hash
- Permissioned issuance with admin/auditor verification
- Issuance-ready deployment on Filecoin mainnet

---

## 🔗 Quick Links

### 🌐 Website
- https://www.filnote.top/

### 🧠 Smart Contracts
- **Mainnet Deployment:** see `/DEPLOYMENTS.md`
- **Source Code:** https://github.com/filnote/FilNoteFEVM

### 🎨 Frontend
- Repo: https://github.com/filnote/FilNoteFEVMFront

### 🛠 Backend API
- Repo: https://github.com/filnote/FilNoteFEVMAPI

### 📄 Reports & Docs
- Milestone 1 Report: `./report/milestone1/1_ExecutiveSummary.md`
- Milestone 2 Report: `./report/milestone2/FilNote_Milestone2_Report.md`
- Legal SOP: `./LEGAL_SOP.md`
- Security Disclosure: `./SECURITY.md`

---

## 🚀 Project Status

FilNote has completed:

### ✅ Milestone 1 – MVP & Feasibility Validation (Calibration Testnet)
- Smart contracts deployed on Calibration
- Frontend MVP for SPs and Investors
- Non-custodial fund flow design
- Legal traceability via IPFS + on-chain hash
- Weekly engineering and testing records

### ✅ Milestone 2 – Mainnet Deployment & Issuance-Ready Validation
- Core contracts deployed and tested on Filecoin mainnet
- Full issuance lifecycle validated under mainnet conditions
- Legal agreement anchoring integrated into production UI
- Admin and auditor operational workflows stabilized
- Frontend, backend, and IPFS services configured for production

> While large-scale capital deployment is gated by business onboarding coordination,  
> **all technical and operational components required for real issuance are now in place.**

---

## 🏗 System Architecture Overview

### Smart Contract Layer

- **FilNoteContract**
  - Note creation and lifecycle management
  - Explicit multi-stage state machine
  - Admin / auditor verification gates

- **ProtocolsContract**
  - Per-issuance investment protocol instances
  - Isolation between individual credit assets
  - DeFi-ready modular design

### Infrastructure Layer

- Frontend: Vue 3 + TypeScript + Quasar + Filecoin AppKit
- Backend: NestJS API + signature-based access control
- Storage: IPFS (Pinata) with encrypted privacy artifacts

---

## 🔐 Security Model

- Solidity ^0.8.22
- OpenZeppelin v5.x
- Reentrancy protection on all fund-related functions
- Role-based access control for admin and auditors
- O(1) auditor lookup via mapping for gas efficiency

Gas optimization example (auditor lookup):

| Auditors | Before | After |
|--------|--------|--------|
| 10 | ~21k gas | ~2.1k gas |
| 100 | ~192k gas | ~2.1k gas |

---

## 📌 Design Philosophy

FilNote follows a **DeFi-ready but not DeFi-dependent** approach:

- Assets are issued with legal binding and full disclosure first
- Cross-protocol liquidity routing is deferred until:
  - stable issuance volume exists
  - standardized risk metadata is available
  - ecosystem partners are ready

This reduces regulatory and systemic risk while preserving future composability.

---

## 📜 License

See [LICENSE](./LICENSE).
