# Agent Security

Agentic systems turn model output into plans, tool calls, state updates, and side effects. That makes them more capable and more dangerous when controls are weak.

## Core Risks

- Unsafe tool execution
- Memory poisoning
- Permission overreach
- Unbounded autonomous loops
- Hidden dependencies on model judgment for security-critical decisions

## Typical Attack Paths

- The agent is steered through malicious prompts or retrieved content.
- A planning step chooses a dangerous tool because the tool catalog is too broad.
- Persistent memory stores attacker-influenced instructions that affect future runs.
- The agent escalates from reading data to changing state because approvals are missing.

## Defenses

- Scope tools to the minimum required action set.
- Add approval checkpoints for state-changing or external actions.
- Keep memory typed, bounded, and reviewable.
- Enforce policy outside the model runtime.
- Record tool calls with context for audit and replay.

## Review Questions

- Which actions can occur without human approval?
- Can the model access secrets or infrastructure credentials directly?
- Is there a separate policy engine for tool authorization?
- Can one compromised task contaminate future tasks through memory?
