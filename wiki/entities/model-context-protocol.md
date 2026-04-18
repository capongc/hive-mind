---
tags: [mcp, protocol, integration, tooling, communication]
sources: [agent-channels.md, sdlc.md]
created: 2026-04-18
updated: 2026-04-18
---

# Model Context Protocol

An open protocol that enables AI agents to connect to and communicate across disparate tools, platforms, and data sources — keeping agents context-aware as they move between environments.

## Role in the AI-Native SDLC

In an [[AI-Native SDLC]], MCP serves as the communication fabric that bridges:
- VS Code (development environment)
- Slack and Discord (real-time messaging)
- GitHub (task tracking and code review)
- Email (ambient triage)

By using MCP, agents maintain shared context across all channels rather than operating in isolated silos.

## Key Use Cases

- Connecting Slack/Discord notifications to VS Code agent actions
- Enabling [[Ambient Triage]] agents to move from email to GitHub Issues seamlessly
- Bridging [[Agent Inbox]] approvals back to deployment pipelines

## Related

- [[Agent Swarm]]
- [[AI-Native SDLC]]
- [[Ambient Triage]]
- [[Human-in-the-Loop]]
