---
tags: [workflow, agent-pattern, orchestration, control-flow, anthropic]
sources: [anthropic-building-effective-ai-agents.md]
created: 2026-04-18
updated: 2026-04-18
---

# Sequential Workflow

An [[AI-Native SDLC]] agent architecture pattern in which tasks follow a predetermined, fixed control flow — each step executes in order, one after the other. Defined by [[Anthropic]] in [[Building Effective AI Agents — Anthropic Whitepaper]] as one of the core single-agent workflow patterns.

## Characteristics

- **Predetermined control flow** — the sequence of steps is defined at design time, not at runtime
- **Predictable** — the same input always produces the same execution path
- **Auditable** — full step-by-step trace is available for review
- **No parallelism** — steps do not execute concurrently

## When to Use

- Compliance and audit requirements demand a traceable, reproducible execution path
- Steps have strict ordering dependencies
- Debugging and explainability are more important than throughput
- The process is well-understood and unlikely to change

## Contrast With

- [[Parallel Workflow]] — fan-out/fan-in for concurrent independent tasks
- [[Evaluator-Optimizer Workflow]] — iterative cycles with feedback loops
- [[Hierarchical Agent Systems]] — dynamic routing by a supervisor at runtime

## Related

- [[AI-Native SDLC]]
- [[Agent Observability]]
- [[Building Effective AI Agents — Anthropic Whitepaper]]
- [[Anthropic]]
