# RAG Security

Retrieval-augmented generation expands model context with external data. It also creates a path for untrusted content to influence answers, actions, and decisions.

## Core Risks

- Retrieval poisoning
- Document-level prompt injection
- Exposure of sensitive chunks through over-broad retrieval
- Embedding leakage and inference risks
- Trust confusion between authoritative and unverified sources

## Typical Attack Paths

- An attacker adds malicious instructions to indexed content.
- Sensitive documents are retrieved because access control is applied after retrieval instead of before it.
- The assistant cites stale or manipulated documents as authoritative.
- Retrieved text is passed directly into tool-invoking prompts.

## Defenses

- Apply authorization before retrieval, not after generation.
- Track provenance for every retrieved chunk.
- Sanitize or down-rank instruction-like content in documents.
- Separate retrieval context from control instructions in prompts.
- Monitor index updates and ingestion pipelines for abuse.

## Review Questions

- Who can write into the corpus?
- How is trust scored for retrieved documents?
- Can users retrieve data across tenant boundaries?
- Are embeddings and vector indexes protected as sensitive assets?
