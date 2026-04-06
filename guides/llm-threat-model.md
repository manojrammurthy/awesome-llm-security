# LLM Threat Model

This guide provides a practical structure for threat modeling LLM-enabled systems.

## 1. Define the System

- Identify the model providers, prompts, retrieval components, tools, memory stores, logs, and user interfaces.
- Map all trust boundaries between users, applications, model runtimes, external content, and execution environments.
- List sensitive assets such as secrets, prompts, transcripts, embeddings, documents, and tool credentials.

## 2. Identify Adversaries

- External attackers using direct prompts
- Internal users abusing over-privileged assistants
- Malicious content authors poisoning retrieval corpora
- Supply chain attackers targeting dependencies or gateways

## 3. Identify Entry Points

- User prompts and file uploads
- Retrieved content and web-browsed pages
- Tool inputs and connector payloads
- Memory stores and cached context
- Administrative consoles and model gateways

## 4. Model Key Threats

- Prompt injection
- Data exfiltration
- Cross-tenant leakage
- Unsafe tool use
- Retrieval poisoning
- Supply chain compromise
- Logging and retention failures

## 5. Estimate Impact

- Confidentiality loss through leaked prompts, data, or transcripts
- Integrity loss through manipulated answers, plans, or actions
- Availability loss through quota abuse, prompt loops, or expensive tool misuse
- Regulatory or contractual impact where sensitive data is involved

## 6. Choose Controls

- Strong authentication and authorization
- Tool-level policy enforcement
- Retrieval sanitation and provenance tracking
- Runtime isolation and least privilege
- Logging, alerting, and incident response playbooks

## 7. Validate Assumptions

- Run adversarial prompt tests
- Simulate malicious retrieval content
- Test tool misuse scenarios
- Review cross-tenant and secret-handling paths

## Output Template

- **Assets:** What matters most
- **Actors:** Who can abuse the system
- **Boundaries:** Where trust changes
- **Threats:** What can go wrong
- **Controls:** What reduces risk
- **Residual risk:** What remains after mitigation
