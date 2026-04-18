---
tags: [multi-agent, agent-architecture, formations, pigment, specialization]
sources: [hivemind-multi-agent-systems.md]
created: 2026-04-18
updated: 2026-04-18
---

# Building a Hivemind — Multi-Agent Systems (Pigment)

**Source:** raw/assets/hivemind-multi-agent-systems.md
**Date ingested:** 2026-04-18
**Type:** article

## Summary

Practical deep-dive on multi-agent systems by [[Pigment]], covering chain vs. graph workflows, the case for specialization over generalism, four architectural formations, and Pigment's own production supervisor implementation. Core premise: task complexity should drive architecture choice.

## Key Claims

- Chain workflows are linear and predictable but cannot handle branching, loops, or parallelism — graph workflows handle all of these
- Specialists outperform generalists: generalist agents require broader context, produce weaker reasoning, slower responses, and more hallucinations
- Emergent behaviors arise from agent collaboration — outcomes that weren't explicitly programmed
- Modularity is a key advantage of multi-agent systems: agents can be added, removed, or swapped without impacting the rest

## Four Architectural Formations

- **Network** — all agents communicate freely; each independently decides next interaction; maximum autonomy
- **Supervisor** — central supervisor coordinates all communication and activates agents; clearest control
- **Hierarchical** — extends supervisor with multiple supervision layers; enables sophisticated control flows
- **Custom** — agents communicate only with specific subsets; predefined partial paths; balances autonomy with constraints

## Pigment's Implementation

Supervisor Agent formation:
- Supervisor Agent (team leader)
- Analyst Agent
- Planner Agent
- Modeler Agent
- Reporter Agent (charts/data publishing)

## Notable Customer Results

- Supercell: P&L updates from 8 days → 4 minutes
- Carta: 80% time reduction on data aggregation
- Fivetran: 12 hours/month saved on executive reporting
- Evenflo: 6 days faster scenario creation

## Entities Mentioned

- [[Pigment]] — publisher; enterprise planning platform; implemented supervisor formation

## Concepts Covered

- [[Agent Swarm]] — multi-agent formations; specialization vs. generalism
- [[Hierarchical Agent Systems]] — supervisor and hierarchical formations
- [[AI-Native SDLC]] — broader context for agent deployment
