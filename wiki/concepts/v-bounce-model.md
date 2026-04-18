---
tags: [v-bounce, methodology, sdlc, testing, traceability, sprints]
sources: [v-bounce.md, sdlc.md]
created: 2026-04-18
updated: 2026-04-18
---

# V-Bounce Model

A software development methodology proposed by [[Cory Hymel]] of [[Crowdbotics]], described in the white paper *"The AI-Native Software Development Lifecycle: A Theoretical and Practical New Methodology"*. It reimagines the traditional V-model from systems engineering for a workflow where AI serves as the primary implementation engine.

## The Shape of the V

```
Requirements ──────────────────── Verification
    │                                   │
  Design ────────────────────── Validation
      │                           │
    Spec ──────────────── Review
          │               │
           └── (BOUNCE) ──┘
             AI Implementation
              (near-instant)
```

The "bounce" is the near-instant time spent at the bottom — AI generates code so rapidly that teams bounce from design directly to validation.

## Core Concepts

- **Human Role Shift:** Humans operate at the top of the V — high-level requirements and final verification/validation. Not execution.
- **Real-Time Test Generation:** AI generates test cases simultaneously as natural language requirements are written. Every requirement is testable the moment it is conceived.
- **Traceability by Design:** Simultaneous req/test creation produces an inherent traceability matrix, simplifying change management and complexity.
- **Sprint Replacement:** V-Bounce directly replaces the traditional 2-week sprint cycle.

## Relationship to Traditional V-Model

The traditional V-model maps verification and validation phases against development stages. V-Bounce preserves the shape but collapses the implementation time at the bottom to near-zero, shifting the human workload entirely to the top arms of the V.

## Related

- [[AI-Native SDLC]]
- [[AI-Native Team]]
- [[Cory Hymel]]
- [[Crowdbotics]]
