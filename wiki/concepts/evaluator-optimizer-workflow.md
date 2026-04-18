---
tags: [evaluator-optimizer, workflow, agent-pattern, quality, iteration]
sources: [anthropic-building-effective-ai-agents.md]
created: 2026-04-18
updated: 2026-04-18
---

# Evaluator-Optimizer Workflow

An [[AI-Native SDLC]] workflow pattern using two AI systems in iterative cycles: a **generator** that creates content and a **evaluator** that assesses it against criteria and provides feedback. The loop repeats until a quality threshold is met. Described in the [[Anthropic]] Building Effective AI Agents whitepaper.

## How It Works

```
Generator → [initial output]
    ↓
Evaluator → [assessment + feedback]
    ↓
Generator → [revised output]
    ↓
(repeat 2–4 cycles)
    ↓
Final output
```

Resembles writer-editor collaboration — specific feedback incorporated into successive drafts.

## When to Use

- Clear evaluation criteria exist
- Iterative refinement demonstrably improves quality
- Content creation requiring nuance (literary translation, professional communications)
- Code generation with security requirements
- Research tasks needing multi-step reasoning with validation

## When to Avoid

- First-attempt quality already meets requirements
- Evaluation criteria are subjective or unclear
- Real-time applications requiring immediate responses
- Simple routine tasks (basic classification)
- Strict token budgets (higher token cost than single-pass)

## Cost Consideration

Higher token cost than single-agent approaches — each cycle consumes additional tokens. Typically runs 2–4 cycles; justified only when quality improvement is measurable and the task warrants it.

## Related

- [[AI-Native SDLC]]
- [[Agent Swarm]]
- [[Anthropic]]
- [[Building Effective AI Agents — Anthropic Whitepaper]]
