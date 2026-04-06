# Prompt Security

Prompt security covers attacks and defenses related to how instructions are represented, merged, overridden, and interpreted inside LLM applications.

## Core Risks

- Direct prompt injection through user input
- Indirect prompt injection through retrieved or browsed content
- System prompt disclosure
- Policy override attempts
- Output shaping for unsafe downstream execution

## Typical Attack Paths

- A user embeds override instructions in a normal-looking request.
- A malicious document introduces hidden instructions that get retrieved into context.
- The model is coaxed into revealing hidden rules, secrets, or chain-of-thought-like artifacts.
- The model generates shell commands, SQL, or workflow steps that downstream systems trust too much.

## Defenses

- Keep instruction layers explicit and separate from user data.
- Use content delimiters and structured inputs rather than raw string concatenation.
- Validate outputs before they reach tools, APIs, or humans acting on them.
- Block or rewrite suspicious instructions in untrusted context.
- Test with adversarial prompts as part of routine evaluation.

## Review Questions

- Can untrusted text alter privileged instructions?
- Are hidden prompts or policies exposed to end users?
- Does downstream logic assume model output is safe?
- Are prompts versioned, reviewed, and tested?
