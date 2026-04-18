---
tags: [agent-swarm, multi-agent, virtual-team, orchestration]
sources: [ai-native.md, sdlc.md, roles.md, agent-channels.md]
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

## Related

- [[AI-Native Team]]
- [[Engineering Lead Role]]
- [[AI-Native SDLC]]
- [[Human-in-the-Loop]]
- [[Model Context Protocol]]
