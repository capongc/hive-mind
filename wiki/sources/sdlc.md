---
tags: [sdlc, ai-native, architecture, aws, mcp, virtual-team]
sources: [sdlc.md]
created: 2026-04-18
updated: 2026-04-18
---

# SDLC

**Source:** raw/assets/sdlc.md
**Date ingested:** 2026-04-18
**Type:** notes

## Summary

Architectural blueprint for an AI-native Software Development Life Cycle. Covers virtual team composition, the MCP communication fabric, AWS deployment automation via AgentCore, and the V-Bounce model replacing traditional sprints.

## Key Claims

- Virtual teams are structured with an Engineering Lead, Developer Agents, and a Test Engineer
- [[Model Context Protocol]] (MCP) connects VS Code, Slack, Discord, and GitHub into a unified fabric
- Ambient triage agents monitor messaging platforms and automatically convert requests into GitHub Issues
- [[AgentCore]] provides a managed, serverless runtime for agents with authentication, networking, and session isolation
- Agents can scan codebases, recommend AWS services, and generate CDK/CloudFormation templates
- The [[V-Bounce Model]] replaces 2-week sprints — humans focus on requirements and validation while agents handle implementation

## Entities Mentioned

- [[CrewAI]] — multi-agent framework for structuring virtual teams
- [[LangGraph]] — alternative multi-agent framework
- [[Model Context Protocol]] — communication bridge across tools and platforms
- [[Agent Inbox]] — HITL interface for approving merges and deployments
- [[AgentCore]] — AWS managed runtime for agent deployment
- [[Claude Code]] — used by Developer Agents for implementation

## Concepts Covered

- [[AI-Native SDLC]] — primary concept; the full lifecycle blueprint
- [[Engineering Lead Role]] — the architect agent at the top of the hierarchy
- [[Human-in-the-Loop]] — HITL approval gates for consequential actions
- [[Ambient Triage]] — automatic triage of unstructured requests into tasks
- [[V-Bounce Model]] — the sprint replacement methodology
- [[Agent Swarm]] — the virtual team as a whole
