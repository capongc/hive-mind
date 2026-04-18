---
tags: [engineering-lead, roles, architecture, delegation, orchestration]
sources: [roles.md, sdlc.md]
created: 2026-04-18
updated: 2026-04-18
---

# Engineering Lead Role

The visionary architect agent at the top of the [[Agent Swarm]] hierarchy. Responsible for translating high-level natural language requirements into detailed design specifications and delegating discrete implementation tasks to specialized developer agents.

## Key Responsibilities

- **Requirement Analysis:** Parses user input (from GitHub Issues, Slack, etc.) and produces a technical blueprint
- **System Management:** Primary interface for user interaction; manages the overall software system state
- **Reuse vs. Build:** Decides when to reuse existing code vs. trigger new implementations
- **Task Delegation:** Distributes discrete tasks to specialized agents (backend, frontend, test engineer)

## Recommended Model

Reasoning-heavy models like **Claude 3.5 Sonnet** are recommended due to the complexity of project planning and system design.

## Position in the Swarm

The Engineering Lead sits at the apex of the [[Agent Swarm]] — it is the orchestrator, not the executor. It sets direction and then gets out of the way while developer agents implement.

## Related

- [[Agent Swarm]]
- [[AI-Native SDLC]]
- [[AI-Native Team]]
- [[V-Bounce Model]]
