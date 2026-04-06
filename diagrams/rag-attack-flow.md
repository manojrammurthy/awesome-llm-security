# RAG Attack Flow Diagram

This diagram shows a common retrieval-augmented generation attack path where attacker-controlled content is indexed, retrieved, and then interpreted as trusted instructions.

## Mermaid Diagram

```mermaid
flowchart TD
    A[Attacker creates poisoned document] --> B[Document enters ingestion pipeline]
    B --> C[Chunking and embedding]
    C --> D[Vector store or search index]
    D --> E[Retriever selects relevant chunks]
    E --> F[Prompt builder merges retrieved text with system and user context]
    F --> G[LLM follows malicious or misleading instructions]
    G --> H[Assistant leaks data or triggers unsafe tool action]

    I[Content provenance checks] -.-> B
    J[Access control before retrieval] -.-> E
    K[Instruction-data separation] -.-> F
    L[Tool policy validation] -.-> H
```

## Attack Stages

1. An attacker places malicious instructions in content that looks like normal documentation, notes, tickets, or webpages.
2. The ingestion pipeline indexes that content without filtering for instruction-like payloads.
3. A later user query retrieves the poisoned chunk because it is semantically relevant.
4. The prompt builder places the chunk next to trusted instructions.
5. The model treats the malicious text as something it should follow.
6. The application returns a manipulated answer or passes unsafe data into a tool layer.

## Defensive Choke Points

- Secure the write path into the corpus.
- Apply authorization before retrieval.
- Track provenance for every chunk.
- Detect and downgrade instruction-like content.
- Keep retrieved data separate from privileged instructions.
- Validate every tool invocation outside the model.
