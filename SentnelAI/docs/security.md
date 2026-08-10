# SentinelAI Security Guidelines & Best Practices

> **Project Phase:** 🚧 Phase 1 — Foundation  
> **Target Event:** Hacker House Goa 2026  
> **Team:** Helping Hands

---

## 1. Zero Private-Key & Credential Handling Policy

SentinelAI is an advisory security platform. Under no circumstances should SentinelAI:
- Request, store, or process user private keys, seed phrases, or private recovery codes.
- Ask users for wallet signatures that grant arbitrary permissions or asset transfers.
- Store sensitive user credentials on server infrastructure.

---

## 2. Secrets Management & API Key Protection

To safeguard infrastructure and third-party API credentials:
- **No Hardcoded Keys:** Never commit API keys, RPC connection secrets, database credentials, or secret tokens directly into source code.
- **Environment Isolation:** Use `.env` files (excluded via `.gitignore`) for local development and secure secrets managers for cloud deployments.
- **Client Key Isolation:** Frontend client builds (Flutter) must never embed backend master API keys or internal database service roles.

---

## 3. Strict Input Validation & Address Sanitization

To protect services from malformed inputs, injection attacks, and resource exhaustion:
- **EVM Address Validation:** Validate Ethereum/EVM hex address formats using standard checksum regex patterns (`^0x[a-fA-F0-9]{40}$`) before querying RPC nodes.
- **Transaction Hash Validation:** Validate 32-byte transaction hash strings (`^0x[a-fA-F0-9]{64}$`).
- **Sanitization:** Strip leading/trailing whitespaces, sanitize URL parameters, and reject unsupported non-hex characters.

---

## 4. External Data Untrusted Input Handling

All data ingested from external sources—including RPC provider nodes, block indexers, contract source APIs, and third-party security feeds—must be treated as **untrusted input**:
- Implement strict schema parsing and defensive null-checking.
- Set strict request timeouts on external network calls to prevent backend execution blocking.
- Gracefully handle unverified contracts or malformed bytecode payloads without service crashes.

---

## 5. API Rate Limiting & Denial-of-Service Defense

To protect backend endpoints and infrastructure:
- Implement client rate limiting (e.g., IP-based token bucket algorithms) on `/api/v1/analyze` endpoints.
- Apply request payload body size caps.
- Cache high-frequency RPC request responses to minimize redundant external network load.

---

## 6. Safe AI Output Handling & Prompt Injection Defense

AI-generated summaries must be handled with appropriate security boundaries:
- **Prompt Injection Defense:** Isolate raw on-chain data and unverified user comments from AI instruction prompts. On-chain metadata passed to the AI engine must be sanitized and clearly delimited as data parameters rather than system instructions.
- **Output Sanitization:** Sanitize AI explanation text before sending it to the client to eliminate script injection risks (XSS).
- **Non-Deterministic Boundary:** Frame all AI output as advisory analysis. Present clear disclaimers that AI responses do not represent financial guarantees or absolute proof of contract safety.

---

## 7. Secure Logging Practices

To protect system integrity while maintaining observability:
- **No PII or Sensitive Logging:** Ensure application logs never capture sensitive user parameters, full request headers containing authorization tokens, or internal credentials.
- **Sanitized Error Logs:** Log error categories and diagnostic codes without dumping full raw system stack traces to public API clients.

---

## 8. Authentication & Authorization Considerations

Future phases introducing user accounts or custom monitoring dashboards must adhere to:
- Stateless JWT or Web3 wallet sign-in validation (e.g., SIWE — Sign-In With Ethereum).
- HTTPS-only TLS encryption for all API communications.
- Secure, HTTP-only cookie parameters where applicable.

---

*Note: These security guidelines serve as mandatory engineering requirements for all future implementation phases of SentinelAI.*
