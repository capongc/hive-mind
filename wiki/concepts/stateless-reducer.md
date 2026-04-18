---
tags: [stateless-reducer, agent-design, 12-factor, state-management, functional]
sources: [12-factor-agents.md]
created: 2026-04-18
updated: 2026-04-18
---

# Stateless Reducer

Factor 12 of the [[12-Factor Agents]] framework. The principle that agents should be designed as pure functions over immutable state — given the same context window (input), they always produce the same next action (output). No hidden internal state; all relevant state lives in the context.

## The Pattern

Borrowed from functional programming and Redux-style state management:

```
(context) → next_step
```

The agent is a reducer: it takes the full accumulated context (all events, tool results, prior steps) and produces the next action. Nothing is stored inside the agent itself.

## Why It Matters

- **Reproducibility:** any run can be replayed by replaying the context
- **Debuggability:** failures are fully diagnosable from the context alone — no hidden state to inspect
- **Resume/pause:** agents can be suspended mid-task and resumed by restoring the context (see Factor 6: Launch/Pause/Resume)
- **Testability:** pure functions are straightforward to unit test

## Relationship to the Agent Loop

In the [[12-Factor Agents]] agent loop:
```python
context = [initial_event]
while True:
  next_step = await llm.determine_next_step(context)  # stateless: context → step
  context.append(next_step)
  result = await execute_step(next_step)
  context.append(result)
```

The LLM call itself is stateless — context in, next step out. All state is accumulated in the context list, not inside the model.

## Related

- [[12-Factor Agents]]
- [[Context Window Management]]
- [[Human-in-the-Loop]]
