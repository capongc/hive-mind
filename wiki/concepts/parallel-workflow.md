---
tags: [workflow, agent-pattern, orchestration, concurrency, anthropic]
sources: [anthropic-building-effective-ai-agents.md]
created: 2026-04-18
updated: 2026-04-18
---

# Parallel Workflow

An [[AI-Native SDLC]] agent architecture pattern in which independent tasks are fanned out to multiple agents simultaneously, then their results are collected (fan-in) for aggregation or synthesis. Defined by [[Anthropic]] in [[Building Effective AI Agents — Anthropic Whitepaper]] as a core multi-agent pattern.

## Fan-Out / Fan-In Structure

```
Input
  ↓
[Orchestrator] — fans out →  [Agent A]
                              [Agent B]
                              [Agent C]
                                ↓
                         [Aggregator] — fan-in → Final output
```

## When to Use

- Tasks can be decomposed into truly independent subtasks
- Throughput and speed matter more than predictability
- Different subtasks require different specializations
- Volume is too large for a single agent to handle sequentially

## Trade-offs

- **Higher token cost** — multiple agents running simultaneously vs. one sequential agent
- **Coordination complexity** — aggregation logic must handle partial failures or inconsistent outputs
- **Less auditable** — emergent behavior from concurrent paths is harder to trace than sequential flow

## Contrast With

- [[Sequential Workflow]] — ordered, one-step-at-a-time control flow
- [[Hierarchical Agent Systems]] — supervisor dynamically routes rather than fanning out uniformly
- [[Evaluator-Optimizer Workflow]] — iterative cycles rather than concurrent branches

## Related

- [[AI-Native SDLC]]
- [[Agent Swarm]]
- [[Context Window Management]]
- [[Building Effective AI Agents — Anthropic Whitepaper]]
- [[Anthropic]]
