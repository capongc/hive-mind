---
tags: [sdlc, ai-native, architecture, lifecycle, deployment]
sources: [sdlc.md, ai-native.md, v-bounce.md, roles.md]
created: 2026-04-18
updated: 2026-04-18
---

# AI-Native SDLC

The full software development lifecycle as restructured for an [[AI-Native Team]], where agents contribute at every stage — planning, design, development, testing, code review, and deployment — and humans focus on requirements, architecture, and validation.

## Lifecycle Stages

### 1. Intake
- [[Ambient Triage]] agents monitor Slack, Discord, and email
- Unstructured requests are automatically converted to GitHub Issues

### 2. Design
- [[Engineering Lead Role]] analyzes requirements and produces detailed design specs
- Human reviews and approves direction via [[Human-in-the-Loop]]

### 3. Implementation
- Developer Agents (using [[Claude Code]], GitHub Copilot) generate code
- The [[V-Bounce Model]] collapses this phase to near-instant

### 4. Testing
- Test Engineer agent generates unit tests in real-time alongside requirements
- Cross-validates AI-generated code before PRs are created

### 5. Review
- Code submitted as GitHub PRs for human verification
- [[Human-in-the-Loop]] gates for consequential merges

### 6. Deployment
- [[AgentCore]] provides a managed serverless runtime on AWS
- Agents generate CDK/CloudFormation IaC templates
- [[Agent Inbox]] surfaces deployment approval requests

## Communication Fabric

[[Model Context Protocol]] (MCP) bridges all tools — VS Code, Slack, Discord, GitHub — so agents remain context-aware across the full lifecycle.

## Orchestration

Teams use [[CrewAI]] or [[LangGraph]] to compose and manage the [[Agent Swarm]].

## Related

- [[AI-Native Team]]
- [[V-Bounce Model]]
- [[Agent Swarm]]
- [[Engineering Lead Role]]
- [[AgentCore]]
- [[Model Context Protocol]]
