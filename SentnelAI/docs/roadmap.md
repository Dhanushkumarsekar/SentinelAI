# SentinelAI Development Roadmap

> **Target Event:** Hacker House Goa 2026  
> **Team:** Helping Hands  
> **Current Phase:** Phase 1 (Foundation)

---

## Roadmap Overview

| Phase | Description | Status |
| :--- | :--- | :--- |
| **Phase 1** | Project Foundation & Architecture Setup | `CURRENT` 🚧 |
| **Phase 2** | Frontend Client Foundation | `PLANNED` 📋 |
| **Phase 3** | Backend API Gateway Foundation | `PLANNED` 📋 |
| **Phase 4** | Blockchain / Web3 Data Integration | `PLANNED` 📋 |
| **Phase 5** | Security Analysis Engine Development | `PLANNED` 📋 |
| **Phase 6** | AI Security Explanation Layer | `PLANNED` 📋 |
| **Phase 7** | Risk Scoring & Security Reporting Engine | `PLANNED` 📋 |
| **Phase 8** | Integration & End-to-End System Testing | `PLANNED` 📋 |
| **Phase 9** | UI/UX Refinement & Visual Polish | `PLANNED` 📋 |
| **Phase 10**| Hackathon Demo Preparation & Presentation | `PLANNED` 📋 |

---

## Detailed Phase Breakdown

### Phase 1: Project Foundation & Architecture Setup
- **Status:** `CURRENT` 🚧
- **Goal:** Establish clean repository scaffolding, establish directory placeholders, define system architecture, document security practices, and create the primary project README.
- **Main Tasks:**
  - Define directory structure (`frontend/`, `backend/`, `ai/`, `contracts/`, `docs/`, `.github/`).
  - Author primary `README.md`, `architecture.md`, `roadmap.md`, `security.md`, and subfolder specifications.
  - Create global `.gitignore` and `LICENSE`.
- **Expected Output:** Fully structured, production-ready documentation scaffold ready for initial code modularization.

---

### Phase 2: Frontend Client Foundation
- **Status:** `PLANNED` 📋
- **Goal:** Initialize cross-platform client workspace using Flutter.
- **Main Tasks:**
  - Initialize Flutter project structure.
  - Build core UI screens (Search Home, Assessment Loading State, Security Report View).
  - Implement responsive layout components and dark theme styling.
- **Expected Output:** Working interactive frontend client with mock state UI navigation.

---

### Phase 3: Backend API Gateway Foundation
- **Status:** `PLANNED` 📋
- **Goal:** Establish Node.js TypeScript API server and routing gateway.
- **Main Tasks:**
  - Set up Node.js TypeScript workspace with Express/Fastify API server.
  - Implement endpoint routing (`/api/v1/analyze`, `/api/v1/health`).
  - Configure CORS, input sanitization middleware, and structured logging.
- **Expected Output:** Operational REST API gateway capable of receiving client requests and returning mock responses.

---

### Phase 4: Blockchain / Web3 Data Integration
- **Status:** `PLANNED` 📋
- **Goal:** Build on-chain data ingestion modules for EVM networks.
- **Main Tasks:**
  - Implement Web3 / Ethers provider connectors for RPC nodes.
  - Build bytecode fetcher, contract verification inspector, and token metadata reader.
  - Implement caching layer for repeated on-chain queries.
- **Expected Output:** Data service capable of pulling live contract bytecode and on-chain metrics given an EVM address.

---

### Phase 5: Security Analysis Engine Development
- **Status:** `PLANNED` 📋
- **Goal:** Construct heuristic security evaluation modules to detect vulnerability patterns.
- **Main Tasks:**
  - Implement static analysis logic for Honeypot detection (unsellable tokens, fee caps).
  - Build contract ownership inspector (mint rights, pause mechanisms, proxy vulnerabilities).
  - Create wallet interaction risk pattern evaluator.
- **Expected Output:** Engine outputting structured JSON security diagnostic flags and risk signals.

---

### Phase 6: AI Security Explanation Layer
- **Status:** `PLANNED` 📋
- **Goal:** Integrate AI translation service to turn technical flags into accessible text.
- **Main Tasks:**
  - Set up Python AI service integration module.
  - Craft system prompts for risk explanation, threat context, and advisory generation.
  - Implement fallback explanations for common deterministic rule matches.
- **Expected Output:** AI module converting technical vulnerability JSON into clear, user-friendly natural language paragraphs.

---

### Phase 7: Risk Scoring & Security Reporting Engine
- **Status:** `PLANNED` 📋
- **Goal:** Formulate risk scoring algorithm and standardize final security report output.
- **Main Tasks:**
  - Develop weighted risk score calculation (0–100 scale).
  - Assign categorical risk levels (`LOW`, `MEDIUM`, `HIGH`, `CRITICAL`).
  - Format output schema combining risk scores, findings, AI explanations, and recommended user actions.
- **Expected Output:** Unified JSON payload ready for frontend rendering.

---

### Phase 8: Integration & End-to-End System Testing
- **Status:** `PLANNED` 📋
- **Goal:** Connect client, backend, analysis engine, and AI module into a cohesive end-to-end pipeline.
- **Main Tasks:**
  - Wire frontend API client to backend orchestration endpoints.
  - Conduct full pipeline execution with test addresses and contract samples.
  - Verify error handling for invalid addresses, RPC timeouts, and unverified contracts.
- **Expected Output:** End-to-end operational application processing live user queries.

---

### Phase 9: UI/UX Refinement & Visual Polish
- **Status:** `PLANNED` 📋
- **Goal:** Refine visual design, animations, risk indicator gauges, and responsive layouts.
- **Main Tasks:**
  - Add visual threat severity badges and interactive risk meters.
  - Improve mobile and web layout responsiveness.
  - Add clear disclaimer overlays and recommendation callouts.
- **Expected Output:** High-polish, hackathon-ready UI experience.

---

### Phase 10: Hackathon Demo Preparation & Presentation
- **Status:** `PLANNED` 📋
- **Goal:** Prepare presentation materials, demo walkthroughs, and live environment staging for Hacker House Goa 2026.
- **Main Tasks:**
  - Stage live demo environment with test cases (legitimate contracts, honeypots, drainers).
  - Record backup video walkthrough of core user flows.
  - Finalize presentation deck highlighting problem, solution, AI explainability, and future potential.
- **Expected Output:** Fully prepared hackathon submission and live presentation demonstration.
