---
tags: [12-factor, engineering-principles, llm, agent-design, production]
sources: [12-factor-agents.md]
created: 2026-04-18
updated: 2026-04-18
---

# Dex Horthy — 12-Factor Agents

**Source:** raw/assets/12-factor-agents.md
**Date ingested:** 2026-04-18
**Type:** open-source guide / engineering principles

## Summary

Engineering principles for building production-grade LLM-powered software, authored by [[Dex Horthy]] of [[HumanLayer]]. Inspired by the 12 Factor Apps methodology. Argues that the "prompt + tools + loop" agentic pattern hits a hard ceiling at 70–80% quality, and that production-quality agents are "mostly just software" — deterministic code with strategically placed LLM steps.

## Key Claims

- Most products billing themselves as "AI Agents" are not all that agentic — they're mostly deterministic code with LLM steps sprinkled at the right points
- Frameworks help builders reach 70–80% quality, but getting past that requires reverse-engineering the framework from scratch — most founders end up starting over
- The fastest path to production-quality AI software is to take small, modular concepts from agent building and incorporate them into existing products
- Even as LLMs get more powerful, there will always be core engineering techniques that make LLM-powered software more reliable, scalable, and maintainable
- Production agents don't follow the "here's your prompt, here's a bag of tools, loop until done" pattern — they are mostly just software

## The 12 Factors

1. Natural Language to Tool Calls
2. Own your prompts
3. Own your context window
4. Tools are just structured outputs
5. Unify execution state and business state
6. Launch/Pause/Resume with simple APIs
7. Contact humans with tool calls
8. Own your control flow
9. Compact errors into context window
10. Small, focused agents
11. Trigger from anywhere, meet users where they are
12. Make your agent a [[Stateless Reducer]]

## The Agent Loop

```python
initial_event = {"message": "..."}
context = [initial_event]
while True:
  next_step = await llm.determine_next_step(context)
  context.append(next_step)
  if (next_step.intent === "done"):
    return next_step.final_answer
  result = await execute_step(next_step)
  context.append(result)
```

## Entities Mentioned

- [[Dex Horthy]] — author; founder of HumanLayer
- [[HumanLayer]] — company building HITL tooling for agents

## Concepts Covered

- [[12-Factor Agents]] — primary concept; the framework itself
- [[Stateless Reducer]] — Factor 12; treat agents as pure functions over immutable state
- [[Human-in-the-Loop]] — Factor 7; contact humans with tool calls
- [[Agent Swarm]] — small focused agents (Factor 10) composing a larger system
