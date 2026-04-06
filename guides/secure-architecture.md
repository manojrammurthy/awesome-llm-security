# Secure Architecture for LLM Systems

This guide outlines architectural patterns that reduce blast radius in production LLM applications.

## Principles

- Keep the model outside the primary trust anchor.
- Enforce policy in deterministic application layers.
- Separate untrusted content from privileged instructions.
- Minimize standing access to data, tools, and infrastructure.
- Design for containment, not perfect model behavior.

## Reference Architecture

### 1. User Interface Layer

- Accept prompts, files, and user actions.
- Apply authentication, rate limits, and coarse input validation.
- Avoid exposing hidden prompts or internal tool metadata.

### 2. Orchestration Layer

- Assemble prompts from typed components.
- Decide whether retrieval, tools, or memory are allowed for the request.
- Enforce policy before any model response can trigger side effects.

### 3. Retrieval Layer

- Apply tenant-aware authorization before fetching documents.
- Track provenance for each chunk.
- Filter or down-rank content that appears instruction-like or low-trust.

### 4. Tool Execution Layer

- Treat model outputs as untrusted requests.
- Validate tool arguments against schemas and policy.
- Require approvals for destructive, financial, or external actions.

### 5. Runtime Isolation Layer

- Run agents and tools in separate trust zones.
- Use short-lived credentials and scoped service accounts.
- Prevent the model runtime from directly holding broad infrastructure secrets.

### 6. Observability Layer

- Log prompt versions, retrieval sources, tool calls, and policy decisions.
- Redact secrets and sensitive user data in telemetry.
- Alert on unusual access, execution, or routing patterns.

## Design Checklist

- Is every side effect mediated by deterministic policy?
- Can untrusted content influence high-privilege actions?
- Are secrets segmented by environment and capability?
- Can one compromised assistant session affect another?
- Are logs and derived artifacts handled as sensitive data?

## Anti-Patterns

- Letting the model directly invoke unrestricted shell or database access
- Applying authorization after retrieval instead of before
- Reusing one provider key across all tenants and environments
- Treating memory as inherently trusted
- Assuming prompt engineering is a substitute for system controls
