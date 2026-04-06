# RAG Security Checklist

This page is a compact checklist companion to the canonical guides.

## Checklist

- Apply authorization before retrieval.
- Track provenance for each retrieved chunk.
- Flag or down-rank instruction-like content in documents.
- Separate retrieved data from privileged prompt instructions.
- Validate every tool invocation outside the model.
- Protect embeddings, indexes, and logs as sensitive assets.

## Canonical Pages

- [RAG security](../categories/rag.md)
- [LLM threat model](llm-threat-model.md)
- [Secure architecture](secure-architecture.md)
- [RAG attack flow diagram](../diagrams/rag-attack-flow.md)
