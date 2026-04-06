# Awesome LLM Security: Incidents, Prompt Injection, RAG, Agents, and AI Supply Chain Risks

![License: MIT](https://img.shields.io/badge/license-MIT-green.svg) ![Markdown](https://img.shields.io/badge/content-Markdown-blue) ![Coverage](https://img.shields.io/badge/incidents-50-orange) ![Focus](https://img.shields.io/badge/focus-LLM%20Security-red)

A curated list of LLM security incidents, prompt injection research, retrieval-augmented generation attack patterns, agent security failures, AI supply chain vulnerabilities, CVE references, and defensive guides for production AI systems.

This repository is designed for security engineers, red teamers, AI platform teams, researchers, and builders who need practical references on large language model security, AI application threats, RAG security, agentic system abuse, and self-hosted AI platform risk.

## Table of Contents

- [Intro](#intro)
- [Why This Repository Exists](#why-this-repository-exists)
- [Timeline](#timeline)
- [Categories](#categories)
- [Highlights](#highlights)
- [RAG Attack Flow](#rag-attack-flow)
- [Repository Layout](#repository-layout)
- [How To Use This Repo](#how-to-use-this-repo)
- [References and Sources](#references-and-sources)
- [Search Topics](#search-topics)
- [Contributing](#contributing)
- [Conventions](#conventions)

## Intro

Large language model security is broader than model alignment or jailbreaks. Real-world AI risk shows up across prompts, retrieval pipelines, vector databases, agent tools, gateways, SDKs, plugins, logs, browser sessions, and surrounding infrastructure.

This repo focuses on:

- LLM security incidents and notable disclosures from 2023 through 2026
- Prompt injection, indirect prompt injection, and system prompt leakage patterns
- RAG security issues including retrieval poisoning, document injection, and data exposure
- Agent security risks such as unsafe tool use, memory poisoning, excessive agency, and approval bypass
- AI supply chain issues in proxies, wrappers, orchestration layers, and self-hosted platforms
- CVE references for AI-adjacent tools, serving stacks, and LLM application infrastructure

## Why This Repository Exists

Teams searching for `LLM security incidents`, `prompt injection examples`, `RAG attack flow`, `AI agent vulnerabilities`, `LiteLLM breach`, `Open WebUI CVEs`, or `LLM CVEs` usually find fragmented blog posts or isolated advisories. This repository puts those topics into one navigable structure with timelines, categories, case studies, diagrams, references, and practitioner guides.

## Timeline

A total of 50 incident, disclosure, and attack-research entries are organized by year.

- [2023 timeline](timeline/2023.md)
- [2024 timeline](timeline/2024.md)
- [2025 timeline](timeline/2025.md)
- [2026 timeline](timeline/2026.md)

## Categories

Canonical category pages:

- [Prompt security](categories/prompt.md)
- [RAG security](categories/rag.md)
- [Agent security](categories/agents.md)
- [Supply chain security](categories/supply-chain.md)

Legacy alias pages kept for navigation stability:

- [Prompt attacks](categories/prompt-attacks.md)
- [RAG attacks](categories/rag-attacks.md)
- [Agent attacks](categories/agent-attacks.md)
- [Data poisoning](categories/data-poisoning.md)
- [Platform abuse](categories/platform-abuse.md)

## Highlights

- [LiteLLM attack](case-studies/litellm-attack.md)
- [Claude command bypass](case-studies/claude-command-bypass.md)
- [Mercor breach linked to LiteLLM](case-studies/mercor-litellm-breach.md)
- [RoguePilot](case-studies/roguepilot.md)
- [Whisper leak](case-studies/whisper-leak.md)
- [LLM threat model guide](guides/llm-threat-model.md)
- [Secure architecture guide](guides/secure-architecture.md)
- [RAG attack flow diagram](diagrams/rag-attack-flow.md)
- [AI and LLM CVE references](references/cves.md)

## RAG Attack Flow

```mermaid
flowchart LR
    A[Attacker-controlled content] --> B[Ingestion or indexing pipeline]
    B --> C[Vector store or document store]
    C --> D[Retriever selects poisoned chunk]
    D --> E[Prompt assembly]
    E --> F[LLM interprets malicious instructions as trusted context]
    F --> G[Unsafe answer or tool invocation]
    G --> H[Data exposure, policy bypass, or harmful action]

    I[Controls] -.-> B
    I -.-> D
    I -.-> E
    I -.-> G
```

For the full breakdown, see [RAG attack flow diagram](diagrams/rag-attack-flow.md).

## Repository Layout

```text
.
├── README.md
├── categories
│   ├── agent-attacks.md
│   ├── agents.md
│   ├── data-poisoning.md
│   ├── platform-abuse.md
│   ├── prompt-attacks.md
│   ├── prompt.md
│   ├── rag-attacks.md
│   ├── rag.md
│   └── supply-chain.md
├── case-studies
│   ├── claude-command-bypass.md
│   ├── litellm-attack.md
│   ├── mercor-litellm-breach.md
│   ├── roguepilot.md
│   └── whisper-leak.md
├── diagrams
│   └── rag-attack-flow.md
├── guides
│   ├── llm-threat-model.md
│   ├── rag-security-checklist.md
│   ├── secure-architecture.md
│   └── secure-llm-architecture.md
├── references
│   ├── cves.md
│   └── sources.md
└── timeline
    ├── 2023.md
    ├── 2024.md
    ├── 2025.md
    └── 2026.md
```

## How To Use This Repo

- Start with the [timeline](timeline/2023.md) files if you want historical examples and notable disclosures.
- Use the [category](categories/prompt.md) pages if you want recurring attack patterns and control ideas.
- Use the [case studies](case-studies/litellm-attack.md) for deeper write-ups of representative failures.
- Use the [guides](guides/llm-threat-model.md) for threat modeling, architecture review, and security checklist work.
- Use the [CVE reference index](references/cves.md) when reviewing self-hosted or AI-adjacent components.
- Use the [source index](references/sources.md) if you want the starter set of public references behind the repository.

## References and Sources

- [CVE index](references/cves.md)
- [Source index](references/sources.md)

## Search Topics

Common topics covered here include:

- LLM security incidents
- AI security case studies
- Prompt injection examples
- Indirect prompt injection
- RAG security checklist
- RAG attack flow
- AI agent security risks
- LLM CVEs
- LiteLLM compromise
- Mercor breach
- Open WebUI vulnerabilities
- Ollama vulnerabilities
- LangChain vulnerabilities
- vLLM vulnerabilities
- Langflow vulnerabilities

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines, scope, style, and how to add new incidents or CVEs.

## Conventions

- Timeline entries are concise and use a consistent format.
- Some entries are public incidents, some are CVE disclosures, and some are notable attack research.
- `CVE: None public` means no public CVE is known or the item is not primarily a CVE-tracked issue.
- Legacy filenames are preserved as aliases where useful, but canonical pages are the shorter filenames.
- The repository is a practical starting point, not a claim of exhaustive coverage.
