---
tags: [agent-architecture, single-agent, perception, reasoning, action]
sources: [anthropic-building-effective-ai-agents.md]
created: 2026-04-18
updated: 2026-04-18
---

# Single-Agent Systems

The foundational [[AI-Native SDLC]] architecture: a single AI agent running a continuous perceive → decide → act loop. Defined by [[Anthropic]] in [[Building Effective AI Agents — Anthropic Whitepaper]] as the recommended starting point before evolving to multi-agent architectures.

## The Loop

```
Perceive (read context, tools, environment)
    ↓
Decide (LLM determines next action)
    ↓
Act (execute tool call, write output, call API)
    ↓
(repeat until done or human intervention)
```

This is the same loop described in [[12-Factor Agents]] as the canonical agent execution pattern.

## When to Use

- Open-ended problems where the control flow cannot be predetermined
- Proving ROI before investing in multi-agent complexity
- Tasks within a single agent's context window and capability envelope
- Simpler domains where a specialist agent handles everything end-to-end

## Limitations

- **Context window ceiling** — long-running tasks exhaust available context
- **Single point of failure** — no redundancy or specialization
- **Throughput** — inherently sequential; no parallelism

## Evolution Path

Anthropic recommends starting with single agents and scaling to [[Hierarchical Agent Systems]] or [[Parallel Workflow]] only when single-agent limitations become measurable blockers.

## Related

- [[Hierarchical Agent Systems]]
- [[Parallel Workflow]]
- [[Sequential Workflow]]
- [[12-Factor Agents]]
- [[Stateless Reducer]]
- [[Building Effective AI Agents — Anthropic Whitepaper]]
- [[Anthropic]]
