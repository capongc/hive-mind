---
tags: [12-factor, engineering-principles, production, llm, agent-design]
sources: [12-factor-agents.md]
created: 2026-04-18
updated: 2026-04-18
---

# 12-Factor Agents

An engineering framework for building production-grade LLM-powered software, authored by [[Dex Horthy]] of [[HumanLayer]]. Inspired by the original [12 Factor Apps](https://12factor.net/) methodology. Addresses the gap between experimental agent frameworks (which hit a quality ceiling at 70–80%) and customer-facing production systems.

## Core Premise

> "The fastest way to get good AI software in the hands of customers is to take small, modular concepts from agent building, and incorporate them into your existing product."

Production agents are not autonomous reasoning loops — they are "mostly just software": deterministic code with LLM steps placed at precisely the right points to create value. The "prompt + tools + loop until done" pattern fails at production scale.

## The 70–80% Ceiling

The typical framework adoption journey:
1. Grab a framework, move fast
2. Reach 70–80% quality
3. Realize 80% isn't good enough for customer-facing features
4. Reverse-engineer the framework to go further
5. Start over from scratch

The 12 factors are the principles that get you past 80% without the restart.

## The 12 Factors

| # | Factor | Core Idea |
|---|---|---|
| 1 | Natural Language to Tool Calls | Convert user intent into structured function invocations |
| 2 | Own your prompts | Direct control over prompt engineering; no framework defaults |
| 3 | Own your context window | Strategic management of token allocation and information |
| 4 | Tools are just structured outputs | Tool calls are deterministic JSON structures |
| 5 | Unify execution state and business state | Sync workflow state with application logic |
| 6 | Launch/Pause/Resume with simple APIs | Simple interfaces for workflow lifecycle management |
| 7 | Contact humans with tool calls | [[Human-in-the-Loop]] as a standard tool call |
| 8 | Own your control flow | Implement decision logic directly, not through framework routing |
| 9 | Compact errors into context window | Efficient error representation within token constraints |
| 10 | Small, focused agents | Specialized, narrow-purpose agents over generalists |
| 11 | Trigger from anywhere | Meet users through multiple integration points |
| 12 | Make your agent a [[Stateless Reducer]] | Agents as pure functions over immutable state |

## Relationship to Other Frameworks

The 12-factor approach is intentionally framework-agnostic. It critiques heavyweight adoption of frameworks like LangGraph, CrewAI, or smolagents — not because frameworks are bad, but because coupling your product architecture to a framework's abstractions makes it hard to push past the quality ceiling.

## Related

- [[Stateless Reducer]]
- [[Human-in-the-Loop]]
- [[Context Window Management]]
- [[Agent Swarm]]
- [[HumanLayer]]
- [[Dex Horthy]]
