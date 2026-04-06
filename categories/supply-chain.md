# Supply Chain Security

LLM systems rely on more than a model provider. SDKs, wrappers, gateways, vector databases, loaders, plugins, and deployment tooling all expand the trust boundary.

## Core Risks

- Malicious or vulnerable dependencies
- Exposed API keys in gateways and proxies
- Unsafe default configurations in wrappers and frameworks
- Indirect compromise through plugins or connectors
- Blind trust in third-party hosted components

## Typical Attack Paths

- A public-facing proxy leaks provider credentials or exposes admin actions.
- A compromised package alters prompt handling, logging, or routing behavior.
- A plugin or connector has broader data access than the core application expects.
- Secrets are copied across multiple orchestration layers without proper isolation.

## Defenses

- Pin and audit dependencies.
- Harden gateways and disable unused admin features.
- Separate secrets by service and environment.
- Review plugin and connector permissions explicitly.
- Maintain an asset inventory of every component in the LLM path.

## Review Questions

- What components sit between the app and the model provider?
- Where are provider keys stored, rotated, and logged?
- Which third-party packages can influence prompts or tool calls?
- Are transitively trusted services part of the security review?
