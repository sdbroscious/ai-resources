# MCP Servers for LLMs: Injection Attacks and Data Exfiltration Risks

## Executive Summary
Model Context Protocol / “Model Control Plane” (MCP) servers materially expand an LLM system’s attack surface. Public security research has documented (a) classical injection vulnerabilities in MCP server implementations (e.g., SQL injection, command injection) and (b) LLM-specific attacks that exploit MCP’s trust boundary (prompt injection, tool poisoning, cross-tool context manipulation) to drive unauthorized actions and data exfiltration.

While few large-scale, confirmed public breaches have been disclosed, reproducible proof-of-concepts and real vulnerabilities indicate MCP-enabled agent systems should be treated as **high-risk** infrastructure and secured accordingly.

---

## 1) Documented Vulnerabilities and Observed Attack Classes

### 1.1 Classical Injection (SQLi / Command Injection)
MCP servers and tools are software services. If they construct SQL queries unsafely, invoke shells with untrusted parameters, or fail to validate inputs, they can be vulnerable to:
- **SQL injection (SQLi)**: bypassing intended read-only controls, modifying or extracting data, and seeding data stores with malicious payloads.
- **Command injection**: executing arbitrary OS commands if tool inputs are passed to shell invocations or unsafe subprocess APIs.

These risks are not theoretical: multiple reference/early MCP implementations have been found with injection vulnerabilities in the wild, and exploit chains have been demonstrated that start with injection and culminate in agent hijack or data theft.

### 1.2 Prompt Injection via MCP
MCP introduces an LLM-specific trust problem: models often implicitly trust:
- tool *descriptions* (metadata),
- tool *responses*,
- content retrieved through tools (docs, web pages, tickets, database rows).

Attackers can embed instructions in these channels that the LLM may interpret as authoritative directives rather than untrusted data (“indirect prompt injection”).

### 1.3 Tool Description Poisoning (“Poisoned Tools”)
A common MCP pattern is to provide tool descriptions to the model to help it decide what to call. If those descriptions contain hidden or obfuscated instructions (e.g., HTML comments, invisible Unicode, embedded JSON), an LLM may follow them. Risks include:
- silent parameter manipulation (e.g., adding a BCC recipient),
- unauthorized tool calls,
- covert data exfiltration (e.g., encode-and-send to an attacker endpoint).

This is particularly dangerous because the user may not see the hidden instruction, but the model does.

### 1.4 Stored Prompt Injection
Analogous to stored XSS:
- an attacker injects malicious instruction text into a persistent data store (e.g., a support ticket, CRM note, wiki page),
- later, an agent retrieves it through an MCP tool,
- the malicious content triggers the agent to misuse other tools (email, file export, HTTP calls), resulting in delayed and stealthy exfiltration.

---

## 2) Data Exfiltration Scenarios

### 2.1 Silent Tool-Based Exfiltration
A malicious tool description or response can instruct the LLM to:
- gather sensitive content (emails, documents, DB results),
- encode it (base64/hex),
- send it to attacker-controlled endpoints (HTTP, email, chat).

Depending on the client UX, the user may only see the “expected” response.

### 2.2 Cross-Tool / Cross-Server Context Poisoning (“Tool Shadowing”)
When multiple MCP servers are connected at once, weak isolation can allow a low-privilege tool to inject instructions that influence subsequent calls to a high-privilege tool (e.g., email, CRM, Git operations). Outcome patterns:
- modifying tool-call JSON to add extra recipients,
- adding additional actions (“also upload this file to …”),
- causing unexpected network egress.

### 2.3 OS-Level Theft via Command Execution
Where command injection exists, exfiltration can bypass the LLM layer entirely:
- read local files (keys, configs),
- dump environment variables and credentials,
- reach internal metadata services,
- pivot into lateral movement depending on network posture.

---

## 3) Risk Assessment (What Makes MCP Different)
Key characteristics that increase risk relative to “LLM-only” systems:
- **Implicit trust** in tool descriptions and outputs.
- **Powerful, composable tooling** (one tool’s output becomes another tool’s input).
- **Potential lack of strong server identity / provenance guarantees** in the tool ecosystem.
- **Agent autonomy**: LLMs may execute multi-step plans without user review.
- **Privilege concentration**: agents often get broad access to email, docs, DBs, ticketing, and code.

---

## 4) Mitigations and Best Practices

### 4.1 Harden MCP Servers Like Production Services
- Use **parameterized queries**; never string-concatenate SQL.
- Strict input validation; reject unexpected characters and formats.
- Avoid shell invocation; if unavoidable, use safe subprocess APIs and fixed argument vectors.
- Patch aggressively; avoid unmaintained reference servers in production.
- Run tools under **least-privilege** service accounts (read-only where possible).
- Add unit tests for injection patterns and boundary cases.

### 4.2 Adopt a Zero-Trust Tool Model
- Maintain an **allowlist** of approved MCP servers and tools.
- Pin versions; verify integrity (signing/hashes) for tool packages/servers.
- Treat third-party/community MCP servers as **untrusted by default**.
- Separate “experimental” tools from production agent environments.

### 4.3 Add LLM-Aware Guardrails (Pre- and Post-Tooling)
- Sanitize tool descriptions: forbid HTML/markdown that can hide content; strip comments and invisible Unicode.
- Enforce strict JSON schemas for tool calls and tool results.
- Policy-check tool-call JSON before execution (e.g., block unexpected recipients, external URLs, file paths).
- Detect prompt-injection patterns in retrieved content and tool responses (heuristics + allowlists).
- Delimit untrusted content in prompts and instruct the model explicitly to treat it as data, not instructions.

### 4.4 Isolation and Monitoring
- Sandbox MCP servers/tools (containers, seccomp, reduced filesystem/network).
- Separate sensitive tools into isolated sessions with constrained context flow.
- Comprehensive logging:
  - tool called, parameters, caller identity, response summary,
  - outbound network destinations,
  - unusual errors / spikes in tool usage.
- Alert on anomalies:
  - new external domains,
  - unexpected BCC/CC,
  - suspicious metacharacters in inputs,
  - repeated failures suggesting probing.

### 4.5 Human-in-the-Loop for High-Risk Actions
- Require explicit user approval for:
  - sending emails/messages,
  - exporting data,
  - making external HTTP requests,
  - running system commands / git pushes.
- Rate-limit tool invocations and add step-level confirmations for multi-action plans.

---

## 5) Practical Recommendations for Adoption
If you are enabling MCP for LLM agents:
1. Start with a **minimal tool set** and least privilege.
2. Treat MCP servers as **tier-0 dependencies**: security review, threat modeling, patch SLAs.
3. Implement **tool-call policy enforcement** in the client/agent runtime.
4. Add **sandboxing + egress controls** (network allowlists).
5. Maintain an incident response playbook specific to agent/tool misuse.

---

## 6) Conclusion
MCP unlocks significant capability, but it also enables credible attack paths for injection and data exfiltration. Security posture must assume adversarial inputs can arrive via tool metadata, tool responses, and retrieved content, and must enforce least privilege, strong validation, isolation, and monitoring to keep agent systems safe.