# SentinelAI System Architecture Specification

> **Project Phase:** 🚧 Phase 1 — Foundation  
> **Status:** Conceptual Architecture Specification  
> **Target Event:** Hacker House Goa 2026 | Team Helping Hands

---

## Executive Architecture Summary

SentinelAI is built as a multi-tier, modular Web3 security platform. The architecture separates raw data ingestion, deterministic heuristic security analysis, natural language explanation generation, and cross-platform presentation into decoupled services.

---

## High-Level Architecture Diagram

```
┌─────────────────────────────────────────────────────────────────┐
│                      PRESENTATION LAYER                         │
│   Flutter Cross-Platform Application (Web / Desktop / Mobile)   │
└────────────────────────────────┬────────────────────────────────┘
                                 │ HTTP / REST API Requests
                                 ▼
┌─────────────────────────────────────────────────────────────────┐
│                      BACKEND API GATEWAY                        │
│   Node.js / TypeScript REST Orchestration & Router              │
└───────────────┬─────────────────────────────────┬───────────────┘
                │                                 │
                ▼                                 ▼
┌───────────────────────────────┐ ┌───────────────────────────────┐
│     BLOCKCHAIN DATA LAYER     │ │   SECURITY ANALYSIS ENGINE    │
│  - EVM RPC Nodes              │ │  - Static Bytecode Heuristics │
│  - Etherscan/Block Indexers   │ │  - Tokenomics & Tax Evaluator │
│  - Token Approval Analyzers   │ │  - Drainer Pattern Detector   │
└───────────────┬───────────────┘ └───────────────┬───────────────┘
                │                                 │
                └────────────────┬────────────────┘
                                 │ Extracted Signals & Metrics
                                 ▼
┌─────────────────────────────────────────────────────────────────┐
│                      AI EXPLANATION LAYER                       │
│   Python LLM Engine / Prompt Translation & Threat Contextualizer │
└────────────────────────────────┬────────────────────────────────┘
                                 │
                                 ▼
┌─────────────────────────────────────────────────────────────────┐
│                   RISK SCORING & REPORT ENGINE                  │
│   Normalizes Risk Ratings (0-100) & Compiles Security Reports   │
└─────────────────────────────────────────────────────────────────┘
```

---

## Detailed Component Specifications

### 1. Presentation Layer (Frontend)
- **Target Tech:** Flutter & Dart
- **Role:** Delivers a clean, cross-platform security search dashboard. Accepts user queries (wallet address, token contract address, transaction hash, or dApp link) and renders real-time security assessment reports, risk meters, detected flags, and plain-language explanations.

### 2. Backend Orchestration Gateway (Backend)
- **Target Tech:** Node.js / TypeScript (REST API)
- **Role:** Serves as the central control gateway. Manages request routing, input sanitization, API rate limiting, response caching, and workflow coordination between data providers, the analysis engine, and the AI explanation service.

### 3. Blockchain Data Layer
- **Target Tech:** EVM RPC interfaces, Web3 indexing APIs (e.g., Etherscan, Alchemy, Covalent)
- **Role:** Fetches raw on-chain state, contract bytecode, source code verification status, transaction traces, transfer logs, and token balance states. Treats all external network data as untrusted input.

### 4. Security Analysis Engine
- **Target Tech:** TypeScript / Python heuristic modules
- **Role:** Executes static code analysis, rules-based pattern matching, and state evaluations to flag known security risks:
  - **Honeypot Logic:** Unsellable token states, high/variable transfer taxes.
  - **Ownership Control:** Renounced status, minting capabilities, transfer pause triggers.
  - **Approval Drainers:** Unlimited token allowances granted to unverified contracts.
  - **Reentrancy & Unsafe Calls:** Vulnerable bytecode or unverified proxy setups.

### 5. AI Explanation Layer
- **Target Tech:** Python NLP / LLM integration service
- **Role:** Takes structured findings and raw diagnostic flags from the Security Analysis Engine and translates them into understandable, jargon-free natural language explanations tailored for everyday Web3 users.

### 6. Risk Scoring Engine
- **Target Tech:** Deterministic scoring module
- **Role:** Synthesizes weighted risk factors into an aggregate Risk Score (0–100) and assigns categorical Risk Levels (`LOW`, `MEDIUM`, `HIGH`, `CRITICAL`).

### 7. Reporting Layer
- **Role:** Packages the risk score, detected anomalies, evidence metrics, AI explanations, and recommended safe actions into a structured payload for frontend rendering.

---

## Data Flow Lifecycle

1. **Query Submission:** User submits a Web3 identifier to the Frontend interface.
2. **Sanitization & Routing:** Backend validates format (regex check for ETH address / Tx hash) and forwards query.
3. **Signal Extraction:** Blockchain Data Layer pulls bytecode, contract verification, and historical logs.
4. **Heuristic Evaluation:** Security Analysis Engine applies vulnerability patterns and calculates security metrics.
5. **Contextual Translation:** AI Explanation Layer receives metrics and generates natural language explanations.
6. **Report Assembly:** Risk Scoring Engine compiles final report payload and sends it back to the client.

---

*Note: This architecture specification represents the target design for future implementation phases. No executable backend services or analysis components have been built in Phase 1.*
