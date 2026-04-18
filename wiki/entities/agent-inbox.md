---
tags: [agent-inbox, hitl, tooling, approval, governance]
sources: [agent-channels.md, sdlc.md]
created: 2026-04-18
updated: 2026-04-18
---

# Agent Inbox

A dedicated interface for [[Human-in-the-Loop]] interactions in agentic workflows. Provides a centralized location where humans can review and approve specific agent actions before they are executed — without needing to context-switch into the development environment.

## Primary Use Cases

- Approving a PR merge before it lands
- Authorizing a production deployment
- Reviewing major code changes flagged by an agent

## Why It Matters

As [[Agent Swarm]] systems become more autonomous, Agent Inbox creates a natural human checkpoint that preserves oversight without blocking the entire pipeline. It surfaces only the decisions that require human judgment.

## Related

- [[Human-in-the-Loop]]
- [[AI-Native SDLC]]
- [[Model Context Protocol]]
