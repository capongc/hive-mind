---
tags: [hitl, governance, human-oversight, approval, agent-safety]
sources: [agent-channels.md, sdlc.md]
created: 2026-04-18
updated: 2026-04-18
---

# Human-in-the-Loop

A governance pattern in agentic systems where a human must review and approve specific agent actions before they are executed. HITL gates are placed at high-stakes decision points to preserve human oversight without interrupting routine automation.

## When HITL Is Applied

Common trigger points in an [[AI-Native SDLC]]:
- Merging a pull request
- Executing a deployment to production
- Major code changes beyond a defined scope
- Infrastructure modifications (e.g. CDK/CloudFormation changes)

## Primary Interface

[[Agent Inbox]] is the dominant tool for HITL interactions — a dedicated interface where the human (e.g. the CTO or Engineering Lead) receives approval requests from agents and can act without leaving their preferred communication channel.

## Related

- [[Agent Inbox]]
- [[Ambient Triage]]
- [[Agent Swarm]]
- [[AI-Native SDLC]]
