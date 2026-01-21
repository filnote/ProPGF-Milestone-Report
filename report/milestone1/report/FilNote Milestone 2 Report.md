FilNote Milestone 2 Report

Mainnet Launch & Real Issuance Validation

Program: Filecoin ProPGF (Batch 1)

Project: FilNote – FIL-Denominated Credit Notes for Storage Providers

Milestone: 02 – Mainnet Launch & Real Issuance Validation

Milestone 2 Date : Oct 2025 – Jan 2026

Team: FilNote Team

Website: https://www.filnote.top/
Core Contracts: https://github.com/filnote/FilNoteFEVM

Frontend: https://github.com/filnote/FilNoteFEVMFront

Backend API: https://github.com/filnote/FilNoteFEVMAPI


1. Executive Summary
Milestone 2 marks FilNote’s transition from a testnet MVP into a mainnet-deployed, operationally ready credit issuance system on Filecoin EVM.
During this phase, the FilNote team completed:
Deployment and testing of smart contracts on Filecoin mainnet,


Stabilization of the full issuance lifecycle under mainnet conditions,


Integration of legal document anchoring and disclosure workflows into the production UI,


Validation of operational readiness for real-world issuance, even though capital deployment is gated by final onboarding coordination between investors and Storage Providers (SPs).


All technical, legal-structural, and operational components required for real issuance are now in place.
Milestone 2 therefore validates FilNote as a mainnet-ready, real-asset issuance primitive, rather than a purely experimental prototype.

2. System Architecture Overview
2.1 Smart Contract Layer
FilNote uses a two-layer contract architecture:
(1) FilNoteContract — Asset Lifecycle Management
Responsibilities:
Note creation (createNote)


Explicit state machine management (7+ states)


Investor entry points and capital flow control


Admin and auditor role enforcement


Event logging for external indexing


Design characteristics:
Explicit lifecycle state transitions


All critical paths protected by validation checks


Investment enabled only after verification


Fully non-custodial — the platform never holds funds


(2) ProtocolsContract — Per-Issuance Investment Instances
Purpose:
Each issuance creates a dedicated protocol instance


Investor funds are bound to specific assets


Enables future composability and modular integrations


Benefits:
Reduced global state coupling


Safer isolation between issuances


Compatible with future DeFi or RWA protocol integration



2.2 Security and Performance Metrics
Category
Metric
Solidity Version
^0.8.22
Security Libraries
OpenZeppelin v5.x
Reentrancy Protection
Enabled on all fund-related functions
Custom Errors
15+
Events
8
Auditor Lookup
O(1) mapping-based

Auditor Gas Optimization Results
By replacing array iteration with mapping lookup:
Auditor Count
Before
After
10
~21,000 gas
~2,100 gas
50
~97,000 gas
~2,100 gas
100
~192,000 gas
~2,100 gas

This optimization is critical for scalable mainnet operations.

3. Frontend, Backend, and IPFS Infrastructure
3.1 Frontend Capabilities
Tech stack:
Vue 3 + TypeScript + Quasar


Pinia state management


Filecoin AppKit wallet integration


Tailwind responsive layout


Bilingual support (EN / CN)


Key features:
Guided note creation flow


Mandatory risk disclosure and SLA preview


Double-confirmation for investment actions


Visualized note status indicators


Dedicated admin and auditor interfaces


Design principles:
Investment actions gated by contract state


Legal document preview required before confirmation


Explicit transaction and error feedback



3.2 Backend and IPFS Services
Backend modules:
NestJS API services


IPFS pinning via FilecoinPIN


Encrypted privacy credential service


Signature-based admin verification


Temporary metadata storage (LowDB)


Data access model:
Contract hash: public


Abridged credential JSON: public


Privacy certificate: encrypted, investment-gated


This structure balances:
Legal disclosure requirements


Privacy protection


Auditability and immutability


4. Development Process and Engineering Phases
Phase 1 — Core Contract Architecture (Sep 2025)
Focus:
Explicit state machine design


Protocol instance separation


Security baseline implementation


Outputs:
Full lifecycle contract logic


Automatic protocol contract deployment



Phase 2 — Frontend Interaction System (Oct 2025)
Focus:
Wallet interaction abstraction


Complex form validation


On-chain/off-chain interaction handling


Outputs:
Fully functional issuance and investment UI


Transaction error handling and user feedback



Phase 3 — Review and Permission System (Nov 2025)
Focus:
Multi-role permission design


Gas cost optimization


Review-driven state transitions


Outputs:
Efficient auditor management


Operational safeguards against accidental approvals



Phase 4 — IPFS and Privacy Layer (Dec 2025)
Focus:
Permanent document storage


Investment-triggered information decryption


Frontend/backend permission coordination


Outputs:
Verifiable legal anchoring model


Compliance-friendly data separation design



5. Mainnet Validation Scope
Under mainnet conditions, the following were validated:
Contract deployment and upgrade safety checks


RPC stability and wallet compatibility


Gas cost acceptability


IPFS accessibility and persistence


End-to-end issuance workflow


All critical paths were tested under real network assumptions, not testnet-specific shortcuts.

6. Storage Provider Workflow Validation
Validation focus:
SP note creation process


Legal binding and verification workflow


Operational coordination procedures


Frontend usability under real conditions


Internal SP environments were used to:
Eliminate uncontrolled business variables


Stress-test workflows


Identify operational boundary cases


External onboarding is scheduled only after system stability is fully verified.

7. DeFi Integration Strategy
FilNote follows a DeFi-ready but not DeFi-dependent design strategy.
Implemented architectural foundations:
Per-asset protocol instances


Explicit asset state machines


Event-driven indexing capability


External query-friendly interfaces


This enables future integrations such as:
Lending collateral recognition


Asset management protocol onboarding


RWA issuance frameworks


However, cross-protocol liquidity routing is intentionally excluded from this milestone to reduce compliance and systemic risks.
8. Technical Validation Metrics
Metric
Status
Mainnet contract stability
✅
Issuance workflow executable
✅
Legal document anchoring
✅
Investment permission gating
✅
Admin and auditor role separation
✅
IPFS document persistence
✅



9. Current Limitations
Recognized constraints:
Jurisdiction-specific legal automation not yet implemented


Secondary market trading not supported


Investor participation remains permissioned


These constraints are intentional safeguards for early-stage credit infrastructure.

10. Conclusion
After Milestone 2, FilNote operates as:
A mainnet-grade issuance system


With legally anchored asset structures


Non-custodial capital flow


Modular protocol-ready architecture


The project has progressed from a prototype into a Filecoin-native credit issuance primitive capable of supporting real-world financing use cases.


11. Public References
Website: https://www.filnote.top/


Core Contracts: https://github.com/filnote/FilNoteFEVM


Frontend: https://github.com/filnote/FilNoteFEVMFront


Backend API: https://github.com/filnote/FilNoteFEVMAPI



