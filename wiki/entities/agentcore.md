---
tags: [agentcore, aws, deployment, infrastructure, serverless]
sources: [sdlc.md]
created: 2026-04-18
updated: 2026-04-18
---

# AgentCore

An AWS managed runtime environment for deploying and running AI agents in production. Provides serverless infrastructure with built-in authentication, networking, and session isolation — removing the need to manually configure cloud infrastructure for the [[Agent Swarm]].

## Capabilities

- Managed serverless compute for agent workloads
- Authentication and identity management for agents
- Networking and session isolation between agent instances
- Integration with `deploy-on-aws` plugin for automated deployments from VS Code

## Role in the AI-Native SDLC

AgentCore is the deployment target at the end of the [[AI-Native SDLC]]. Agents can scan the codebase, recommend AWS services (App Runner, RDS, etc.), and generate CDK or CloudFormation templates — then deploy via AgentCore.

## Related

- [[AI-Native SDLC]]
- [[Agent Swarm]]
