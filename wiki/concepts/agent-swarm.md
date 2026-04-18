---
tags: [agent-swarm, multi-agent, virtual-team, orchestration, architecture-patterns]
sources: [ai-native.md, sdlc.md, roles.md, agent-channels.md, anthropic-building-effective-ai-agents.md, hivemind-multi-agent-systems.md]
created: 2026-04-18
updated: 2026-04-18
---

# Agent Swarm

The collective of specialized AI agents that form a virtual software development team. Each agent has a defined role; together they cover the full [[AI-Native SDLC]] from requirements through deployment.

## Canonical Composition

| Agent | Role |
|---|---|
| [[Engineering Lead Role]] | Translates requirements into design specs; delegates to other agents |
| Developer Agents | Generate code using tools like [[Claude Code]] or GitHub Copilot |
| Test Engineer | Autonomously generates unit tests and cross-validates AI-generated code |

## Orchestration Frameworks

- [[CrewAI]] — role-based multi-agent framework
- [[LangGraph]] — graph-based agent workflow framework

## Communication Fabric

Agents stay context-aware across tools via [[Model Context Protocol]] (MCP), which bridges Slack, Discord, GitHub, and VS Code into a unified environment.

## The Competitive Unit

Per [[AI-Native Team]] doctrine: the competitive unit is **team × agents** — not headcount alone. The swarm multiplies human output rather than replacing human judgment.

## Architectural Formations (per Pigment)

[[Pigment]] identifies four swarm formations based on coordination style:

| Formation | Description |
|---|---|
| **Network** | All agents communicate freely; each independently decides next interaction |
| **Supervisor** | Central supervisor coordinates all communication and activates agents |
| **Hierarchical** | Multiple layers of supervisors; enables sophisticated modular control |
| **Custom** | Agents communicate only with specific subsets; predefined partial paths |

## Why Specialists Over Generalists

Per [[Pigment]] and [[Anthropic]]: generalist agents require broader context, produce weaker reasoning, slower responses, and more hallucinations. Specialists are more efficient and enable emergent behaviors — collaborative outcomes that weren't explicitly programmed.

Per [[Anthropic]] internal research: multi-agent systems outperform single-agent by **90.2%** on tasks requiring multiple simultaneous directions. However, they cost 10–15x more tokens — business value must justify the complexity.

## 12-Factor Perspective

[[12-Factor Agents]] (Factor 10: Small, Focused Agents) aligns with this: narrow-purpose specialist agents over generalists. The swarm is composed of many small agents, each doing one thing well, rather than one large agent doing everything.

## Related

- [[AI-Native Team]]
- [[Engineering Lead Role]]
- [[AI-Native SDLC]]
- [[Human-in-the-Loop]]
- [[Model Context Protocol]]
- [[Hierarchical Agent Systems]]
- [[12-Factor Agents]]
- [[Pigment]]
- [[Anthropic]]
