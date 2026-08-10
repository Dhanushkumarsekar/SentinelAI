# SentinelAI 🛡️

**AI-Powered Web3 Security Detective**

---

## Overview

**SentinelAI** is an AI-powered Web3 security platform engineered to empower users by identifying, interpreting, and explaining security risks across decentralized applications (dApps), smart contracts, tokens, wallet addresses, and blockchain transactions.

Navigating Web3 today requires interacting with opaque smart contracts, complex transaction data, and rapidly evolving token ecosystems. For average users, assessing whether a smart contract contains malicious logic, whether a token is a honeypot, or whether a transaction request is a drainer scam is extremely difficult. Most existing security tools produce raw technical diagnostic outputs or static risk scores without providing meaningful context.

SentinelAI bridges this accessibility gap. By combining real-time Web3 security signal extraction with an intelligent AI explanation layer, SentinelAI translates complex cryptographic and state analysis into clear, human-readable insights. Instead of leaving users with cryptic data, SentinelAI answers four fundamental questions:
- **What is risky?**
- **Why is it risky?**
- **How serious is the risk?**
- **What should the user do?**

---

## Problem

Web3 adoption is frequently compromised by security threats that target both technical vulnerabilities and user comprehension gaps. Key challenges include:

- **Smart Contract Vulnerabilities:** Hidden reentrancy vectors, unsafe delegate calls, unverified source code, and arbitrary ownership control.
- **Token Scams:** Honeypots, hidden mint functions, excessive buy/sell taxes, non-transferable tokens, and liquidity pull risks.
- **Malicious & Suspicious Contracts:** Wallet drainers, fake staking protocols, phishing proxies, and unannounced contract upgrades.
- **Suspicious Transaction Behavior:** Unverified approvals, high-value transfer permissions to newly deployed addresses, and unusual interaction velocity.
- **Fake or Impersonation Tokens:** Counterfeit tokens mimicking legitimate project tickers to deceive investors.
- **Complex Blockchain Security Data:** Technical security reports, bytecode disassembly, and raw event logs that are inaccessible to non-technical users.
- **Lack of Actionable Explanations:** Traditional tools report raw flags without guiding the user on how to safely navigate or mitigate identified risks.

---

## Solution

SentinelAI functions as an automated Web3 Security Detective. The platform processes user inputs—such as a wallet address, token contract, transaction hash, or dApp URL—and produces a structured, human-understandable security assessment.

### Intended Workflow

```
User provides Address / Hash / Token / Contract
                      │
                      ▼
   SentinelAI Collects Security Signals
   (On-chain data, contract code, tx history)
                      │
                      ▼
        System Analyzes Available Data
   (Static analysis, pattern matching, rules)
                      │
                      ▼
       Security Rules & Detection Engine
  (Identifies honeypots, drainers, vulnerabilities)
                      │
                      ▼
            AI Explanation Layer
     (Translates technical findings into text)
                      │
                      ▼
  User Receives Structured Security Report
  (Risk level, score, findings & recommended actions)
```

> *Note: The workflow outlined above represents the planned architecture and will be implemented progressively across future development phases.*

---

## Core Features

### 1. Smart Contract Security Analysis
Extracts smart contract metadata, bytecode characteristics, and verification status to evaluate structural safety and flag known vulnerability patterns.

### 2. Token Risk Analysis
Evaluates tokenomics parameters, minting rights, fee structures, holder distributions, and liquidity dynamics to flag honeypots, rug-pull indicators, and fee manipulation mechanisms.

### 3. Transaction Analysis
Inspects transaction payloads, call stacks, approval grants, and transfer destinations to detect malicious transaction patterns and wallet-draining signatures.

### 4. Wallet Risk Analysis
Analyzes historical wallet behavior, interaction profiles, known risk tags, and counterparty associations to assess wallet trust profiles.

### 5. AI Security Explanation
Utilizes domain-tuned language modeling to contextualize complex technical vulnerabilities, explaining the mechanics and implications of detected threats in plain language.

### 6. Risk Score
Generates a normalized, intuitive risk rating paired with a granular breakdown of contributing factors.

### 7. Security Report
Delivers an actionable report featuring:
- **Overall Risk Level** (e.g., LOW, MEDIUM, HIGH, CRITICAL)
- **Risk Score** (0–100 scale)
- **Detected Issues & Anomalies**
- **Evidence & Signal Breakdown**
- **Plain-Language Explanation**
- **Recommended User Actions**

---

## Example User Experience

> **IMPORTANT:** *The following example is purely fictional and intended solely to demonstrate the target user experience. Address strings and values used are non-functional placeholders.*

### User Input
```
Target Input: 0x1234...abcd (Smart Contract Address)
```

### SentinelAI Assessment Output

```text
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SENTINEL AI — SECURITY ASSESSMENT REPORT (FICTIONAL EXAMPLE)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Risk Level : HIGH
Risk Score : 82 / 100

Detected Concerns:
- [CRITICAL] Unrestricted Minting Functionality Detected
- [WARNING]  Contract Owner Can Pause Transfers Arbitrarily
- [WARNING]  Sell Tax Configurable Up To 99%

Why This Matters:
The contract code permits the creator to print unlimited new tokens 
at any time without user approval. Additionally, the owner retains 
the ability to block transactions or raise sell fees up to 99%, 
which could prevent you from selling your tokens (Honeypot risk).

Recommended Action:
DO NOT interact with this contract or approve token transactions. 
Avoid committing funds until independent code audit verification is provided.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Planned Architecture

The system is structured across modular layers, facilitating scalable processing from raw blockchain RPC requests to AI-assisted report generation:

```
[ User ]
   │
   ▼
[ Frontend Layer ] ──────── (Flutter / Cross-Platform Web & Mobile)
   │
   ▼
[ Backend API ] ────────── (REST Orchestration & Gateway)
   │
   ├────────────────────────┐
   ▼                        ▼
[ Blockchain Data ]    [ Security Analysis Engine ]
(RPC / Indexers)       (Rules, Heuristics, Pattern Matching)
   │                        │
   └───────────┬────────────┘
               ▼
[ AI Explanation Layer ] ─ (Contextual NLP & Explanation Generation)
               │
               ▼
[ Risk Assessment & Reporting Engine ]
               │
               ▼
[ Structured Security Report Delivered to User ]
```

---

## Technology Direction

To maintain flexibility during development, SentinelAI evaluates candidate technology stacks tailored for performance, security, and developer velocity:

- **Frontend:** [Flutter](https://flutter.dev/) & Dart (providing unified cross-platform support across Web, Mobile, and Desktop).
- **Backend:** Node.js, TypeScript, REST APIs (delivering typed, performant asynchronous request orchestration).
- **AI Engine:** Python, Machine Learning models, LLM integration for security explanation generation.
- **Blockchain Data:** EVM RPC providers, block indexers, and Web3 data APIs.
- **Database:** Relational or Document Store (to be selected based on caching and indexing requirements).
- **Security Engineering:** Input sanitization, API rate limiting, robust secret management, and strict validation of blockchain parameters.

> **Note:** *No external dependencies or code frameworks have been installed during Phase 1. This section documents the intended technological direction.*

---

## Project Architecture

The repository is organized into distinct domain packages to support modular development:

```
SentinelAI/
│
├── README.md                 # Primary project documentation & overview
├── .gitignore                # Global version control exclusions
├── LICENSE                   # Open-source license file
│
├── frontend/                 # User interface & cross-platform client app
│   └── README.md
│
├── backend/                  # API server, data ingestion & orchestration
│   └── README.md
│
├── ai/                       # AI models, prompts, static analysis & ML logic
│   └── README.md
│
├── contracts/                # Smart contract specs & Web3 integration assets
│   └── README.md
│
├── docs/                     # Architecture, security & roadmap documentation
│   ├── architecture.md
│   ├── roadmap.md
│   └── security.md
│
└── .github/                  # CI/CD workflows and repository automation
    └── workflows/
        └── README.md
```

---

## Development Roadmap

| Phase | Title | Focus Area | Status |
| :--- | :--- | :--- | :--- |
| **Phase 1** | **Project Foundation & Architecture** | Scaffolding, repository setup, architecture & docs | `CURRENT` 🚧 |
| **Phase 2** | **Frontend Foundation** | Client setup, UI component hierarchy & layouts | `PLANNED` |
| **Phase 3** | **Backend API Foundation** | REST API structure, routing, middleware & logging | `PLANNED` |
| **Phase 4** | **Blockchain / Web3 Integration** | RPC connections, contract fetching & data indexers | `PLANNED` |
| **Phase 5** | **Security Analysis Engine** | Heuristic rules, vulnerability detection logic | `PLANNED` |
| **Phase 6** | **AI Explanation Layer** | Prompt engineering, security context translation | `PLANNED` |
| **Phase 7** | **Risk Scoring & Reports** | Score algorithms, report generation & formatting | `PLANNED` |
| **Phase 8** | **Integration & Testing** | End-to-end integration, mock tests & API verification | `PLANNED` |
| **Phase 9** | **UI/UX Polish** | Visual refiners, risk indicators & responsive design | `PLANNED` |
| **Phase 10**| **Hackathon Demo Prep** | Demo scripts, live environment staging & submission | `PLANNED` |

---

## Security Principles

SentinelAI adheres to strict security defaults across design and implementation:

1. **Zero Key Storage:** SentinelAI never requests, stores, or processes user private keys or seed phrases.
2. **Strict Input Validation:** All blockchain addresses, hashes, and inputs are verified prior to execution.
3. **Untrusted Data Handling:** External data fetched from RPC nodes or third-party indexers is sanitized as untrusted input.
4. **Environment Isolation:** Secrets, API tokens, and configuration values must be managed via isolated environment variables.
5. **Rate Limiting & Protection:** APIs must enforce rate limiting to prevent abuse and denial-of-service risks.
6. **Non-Deterministic Caution:** AI findings are presented as contextual analytical assistance, not absolute truth.
7. **Transparent Signals:** Security warnings must highlight underlying evidence and raw signals wherever feasible.

---

## Responsible AI

SentinelAI is built around responsible AI design for Web3 security:

- **Evidence-Based Insights:** Distinguishes verified on-chain facts from inferred AI observations.
- **Uncertainty Communication:** Explicitly reports low-confidence scenarios when data is incomplete or unverified.
- **Mitigation of False Positives:** Calibrates detection thresholds to reduce unfair categorization of legitimate novel projects.
- **Explainable Reasoning:** Outlines the *why* behind every risk flag to foster user security literacy.
- **User Empowerment:** Encourages independent verification for financial and high-consequence operations.
- **Strict Privacy Preservation:** Operates without requesting sensitive credential information.

---

## Hackathon Goal

SentinelAI is being actively developed for **Hacker House Goa 2026** by **Team Helping Hands**.

Our goal is to build a functional prototype demonstrating how artificial intelligence can transform complex Web3 security signals into intuitive, accessible, and actionable safeguards for everyday users.

### Key Evaluation Focus Areas:
- **Functional Execution:** Robust, reliable signal retrieval and risk evaluation.
- **User Experience:** Seamless input flow and clear visual reporting.
- **Explainable Analysis:** Meaningful, plain-language risk breakdowns.
- **Practical Utility:** Addressing real-world Web3 threats (honeypots, drainers, unverified contracts).

---

## Team

- **Team Name:** Helping Hands
- **Project:** SentinelAI
- **Hackathon:** Hacker House Goa 2026

---

## Previous Work

Members of Team Helping Hands bring hands-on hardware, embedded systems, and mobile software engineering experience from previous projects:

- **GloveCom:** A wearable sign-language translation system that integrated an ESP32 micro-controller smart glove with a custom Flutter mobile app for real-time gesture translation.

> **Clarification:** *GloveCom is a previously completed project by team members and is cited solely as evidence of prior technical execution. SentinelAI is our official, net-new entry for Hacker House Goa 2026.*

---

## Project Status

**Current Status:** `🚧 Phase 1 — Foundation`

The repository is currently in its initial architecture and setup phase. Core functionality and component layers will be constructed incrementally in alignment with the development roadmap.

---

## Disclaimer

SentinelAI is an analytical security-assistance tool. It does not guarantee that any smart contract, token, wallet address, dApp, or transaction is completely safe or malicious. Security analysis produced by SentinelAI should be independently verified before making financial, operational, or security-critical decisions.

---

## License

This project is made available under the [MIT License](LICENSE). Final licensing decisions and terms will be governed by Team Helping Hands.

