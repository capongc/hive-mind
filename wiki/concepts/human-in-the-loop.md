---
tags: [hitl, governance, human-oversight, approval, agent-safety]
sources: [agent-channels.md, sdlc.md, 12-factor-agents.md, adrej-karpathy-llmwiki.md]
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

## HITL as a Tool Call (12-Factor Agents)

[[12-Factor Agents]] (Factor 7) reframes HITL as a first-class engineering pattern: contacting a human is just another tool call. Rather than treating human approval as an exceptional flow, it's a structured output — the agent calls a "contact_human" tool, execution pauses, and resumes when the human responds. This integrates cleanly with Factor 6 (Launch/Pause/Resume) and Factor 12 ([[Stateless Reducer]]) — the context is preserved so the agent can resume exactly where it left off.

## HITL in the LLM Wiki Pattern

[[Andrej Karpathy]]'s [[LLM Wiki Pattern]] positions the human as curator and director — not executor. The human's job is sourcing, directing analysis, and asking good questions. The LLM handles everything else. This is a soft HITL: the human is always in the loop on *what* to process, but delegates *how* to the LLM.

## Related

- [[Agent Inbox]]
- [[Ambient Triage]]
- [[Agent Swarm]]
- [[AI-Native SDLC]]
- [[12-Factor Agents]]
- [[Stateless Reducer]]
- [[LLM Wiki Pattern]]
