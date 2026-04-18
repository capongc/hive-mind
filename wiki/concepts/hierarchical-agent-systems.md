---
tags: [hierarchical, supervisor, multi-agent, architecture, orchestration]
sources: [anthropic-building-effective-ai-agents.md, hivemind-multi-agent-systems.md]
created: 2026-04-18
updated: 2026-04-18
---

# Hierarchical Agent Systems

A multi-agent architecture pattern where a central supervisor agent routes tasks to specialist agents and synthesizes their responses. Mirrors effective human organizational structures: specialists focus on their domain while coordinators handle task distribution and integration.

## How It Works

- Supervisor analyzes incoming requests, routes to appropriate specialists, synthesizes responses
- Subagents are treated as tools — supervisor uses tool-calling to decide which to invoke
- Subagents can have their own subagents; supervisor only interacts with team leaders
- Creates clear chains of responsibility that scale with organizational complexity

## Implementation Variations

| Variation | Description |
|---|---|
| Full orchestration | Supervisor controls all user interactions and task execution |
| Routing-focused | Specializes in delegation; hands off user communication to specialists |
| Hybrid coordination | Selectively involves supervisor based on task complexity |

## Key Challenge: Context Management

As the orchestrator accumulates context across interactions, it faces context window overflow, degraded reasoning, and coordination failures. Mitigations: context editing, memory tools, tool output pagination/truncation. See [[Context Window Management]].

## Formations (per Pigment)

Pigment's framing of the same pattern identifies four variants:
- **Supervisor** — single central coordinator
- **Hierarchical** — multiple layers of supervisors
- **Network** — peer-to-peer; no central authority
- **Custom** — partial predefined paths with selective autonomy

## Economics

Multi-agent systems consume significantly more tokens than single agents. [[Anthropic]] guidance: justify the cost against business value for high-complexity, high-value tasks.

## Related

- [[Agent Swarm]]
- [[Engineering Lead Role]]
- [[Context Window Management]]
- [[Agent Observability]]
- [[AI-Native SDLC]]
- [[Human-in-the-Loop]]
