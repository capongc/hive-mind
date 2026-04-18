---
tags: [agent-channels, mcp, communication, slack, github, hitl]
sources: [agent-channels.md]
created: 2026-04-18
updated: 2026-04-18
---

# Agent Channels

**Source:** raw/assets/agent-channels.md
**Date ingested:** 2026-04-18
**Type:** notes

## Summary

Overview of the primary messaging and communication channels used in virtual AI team setups, and how [[Model Context Protocol]] bridges them into a unified, context-aware development environment.

## Key Claims

- Slack and Discord are the real-time hubs; Claude for Slack enables in-channel notifications and commands
- GitHub Issues and PRs serve as the core async task-tracking layer — the "Jira-like" channel for developer agents
- [[Agent Inbox]] is the preferred interface for [[Human-in-the-Loop]] approvals before high-stakes actions
- Email is used for ambient triage — agents monitor inboxes and convert requests into structured GitHub Issues
- [[Model Context Protocol]] (MCP) connects all messaging platforms to the development environment

## Entities Mentioned

- [[Agent Inbox]] — dedicated HITL interface for approving agent actions
- [[Model Context Protocol]] — protocol for bridging messaging platforms with development tooling

## Concepts Covered

- [[Human-in-the-Loop]] — approval gate before agents execute consequential actions
- [[Ambient Triage]] — agents automatically converting unstructured messages into structured tasks
- [[Agent Swarm]] — the multi-agent virtual team this communication fabric serves
