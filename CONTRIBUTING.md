# Contributing

Thanks for contributing to `awesome-llm-security`.

## Scope

Good contributions include:

- LLM security incidents with public reporting
- AI-adjacent CVEs relevant to model serving, gateways, orchestration, retrieval, or self-hosted platforms
- Prompt injection, RAG, agent, and supply-chain case studies
- Defensive guides, diagrams, and checklists

Out of scope unless strongly tied to this repository:

- General AI product news without a security angle
- Pure model benchmark updates
- Unverified rumors with no credible public reporting

## Style Guide

- Use clean Markdown with short sections and readable bullets.
- Prefer exact dates such as `March 31, 2026` over relative dates.
- Keep incident entries concise: category, class, summary, CVE status, and lesson.
- Distinguish clearly between confirmed facts and inference.
- When a case is still under investigation, say that directly.

## Sources

- Prefer primary sources when available: vendor advisories, NVD, official incident write-ups, or security advisories.
- Reputable reporting is acceptable for public incident timelines when primary disclosure is incomplete.
- Add links to [references/sources.md](references/sources.md) or [references/cves.md](references/cves.md) when extending the repo.

## File Conventions

- Put yearly incident collections in `timeline/`.
- Put recurring topic overviews in `categories/`.
- Put deeper attack write-ups in `case-studies/`.
- Put diagrams in `diagrams/`.
- Put reusable defensive material in `guides/`.
- Put source catalogs in `references/`.

## Canonical Pages

Use these as the main pages for ongoing edits:

- `categories/prompt.md`
- `categories/rag.md`
- `categories/agents.md`
- `categories/supply-chain.md`
- `guides/llm-threat-model.md`
- `guides/secure-architecture.md`

Some legacy filenames remain in place as aliases to avoid breaking links.

## Pull Request Checklist

- The content is clearly relevant to LLM or AI application security.
- Dates are concrete and accurate.
- CVE references link to NVD or an equivalent primary advisory.
- Claims are attributed when the facts are still emerging.
- The new file fits the existing repository structure.
