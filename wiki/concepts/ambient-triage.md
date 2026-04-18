---
tags: [ambient-triage, automation, task-management, email, slack]
sources: [agent-channels.md, sdlc.md]
created: 2026-04-18
updated: 2026-04-18
---

# Ambient Triage

An agentic automation pattern where agents passively monitor unstructured communication channels (email, Slack, Discord) and automatically convert incoming requests into structured development tasks — typically GitHub Issues.

## How It Works

1. Agent monitors messaging platform or email inbox continuously
2. Incoming message or email is parsed for intent and context
3. Agent creates a structured GitHub Issue with relevant metadata
4. Human reviews or the [[Engineering Lead Role]] picks up the task for delegation

## Value

Eliminates the overhead of manual task intake. Unstructured human communication flows directly into the development pipeline without requiring a dedicated product manager or project coordinator.

## Related

- [[Human-in-the-Loop]]
- [[Agent Swarm]]
- [[Model Context Protocol]]
- [[AI-Native SDLC]]
