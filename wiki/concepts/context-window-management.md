---
tags: [context-window, token-management, agent-design, 12-factor, observability]
sources: [12-factor-agents.md, anthropic-building-effective-ai-agents.md]
created: 2026-04-18
updated: 2026-04-18
---

# Context Window Management

The discipline of deliberately controlling what information occupies the LLM's context window at any point during agent execution. Addressed by both [[12-Factor Agents]] (Factor 3: Own your context window; Factor 9: Compact errors) and the [[Anthropic]] Building Effective AI Agents whitepaper (as the key challenge in hierarchical systems).

## Why It Matters

The context window is the LLM's entire working memory. Poor management leads to:
- **Context window overflow** — critical information gets truncated
- **Degraded reasoning** — too much irrelevant content dilutes signal
- **Coordination failures** — agents lose coherence across extended interactions
- **Runaway token costs** — unnecessary context multiplies cost across every call

## Key Techniques

**Context editing**
- Automatically clear stale tool calls and results as the context grows
- Keep conversation flow intact while removing noise
- Prevent context exhaustion without losing thread continuity

**Memory tools**
- Store and retrieve information outside the context window
- File-based persistence that survives across sessions
- The agent writes to memory; reads from it when needed

**Tool output pagination/truncation**
- Cap tool responses at manageable sizes (~25,000 tokens per Anthropic guidance)
- Include pagination, range selection, filtering options in all tools
- Never let a single tool call flood the context

**Strategic loading (Factor 3 / Factor 13)**
- Pre-fetch all context you *might* need before starting the agent loop
- Be deliberate about what goes in — not everything from every source
- Compact errors into minimal representations (Factor 9) rather than full stack traces

## In the Stateless Reducer Model

From [[12-Factor Agents]]: since the agent is a [[Stateless Reducer]] and all state lives in the context, context management IS state management. What's in the context determines what the agent knows and how it reasons.

## Related

- [[12-Factor Agents]]
- [[Stateless Reducer]]
- [[Agent Observability]]
- [[Hierarchical Agent Systems]]
- [[Dex Horthy — 12-Factor Agents]]
- [[Building Effective AI Agents — Anthropic Whitepaper]]
