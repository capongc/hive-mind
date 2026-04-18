# 12-Factor Agents — Principles for Building Reliable LLM Applications

**Source:** https://github.com/humanlayer/12-factor-agents
**Author:** Dex (HumanLayer)
**License:** Content: CC BY-SA 4.0 | Code: Apache 2.0
**Type:** Open-source guide / engineering principles

---

*In the spirit of [12 Factor Apps](https://12factor.net/).*

> Missed the AI Engineer World's Fair? Catch the talk here: https://www.youtube.com/watch?v=8kMaTybvDUw
>
> Looking for Context Engineering? Jump straight to factor 3.
>
> Want to contribute to `npx/uvx create-12-factor-agent` — check out the discussion thread.

---

Hi, I'm Dex. I've been hacking on AI agents for a while.

**I've tried every agent framework out there**, from the plug-and-play crew/langchains to the "minimalist" smolagents of the world to the "production grade" langraph, griptape, etc.

**I've talked to a lot of really strong founders**, in and out of YC, who are all building really impressive things with AI. Most of them are rolling the stack themselves. I don't see a lot of frameworks in production customer-facing agents.

**I've been surprised to find** that most of the products out there billing themselves as "AI Agents" are not all that agentic. A lot of them are mostly deterministic code, with LLM steps sprinkled in at just the right points to make the experience truly magical.

Agents, at least the good ones, don't follow the "here's your prompt, here's a bag of tools, loop until you hit the goal" pattern. Rather, they are comprised of mostly just software.

So, I set out to answer:

> **What are the principles we can use to build LLM-powered software that is actually good enough to put in the hands of production customers?**

Welcome to 12-factor agents.

---

## The 12 Factors

Even if LLMs continue to get exponentially more powerful, there will be core engineering techniques that make LLM-powered software more reliable, more scalable, and easier to maintain.

1. [Factor 1: Natural Language to Tool Calls](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-01-natural-language-to-tool-calls.md)
2. [Factor 2: Own your prompts](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-02-own-your-prompts.md)
3. [Factor 3: Own your context window](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-03-own-your-context-window.md)
4. [Factor 4: Tools are just structured outputs](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-04-tools-are-structured-outputs.md)
5. [Factor 5: Unify execution state and business state](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-05-unify-execution-state.md)
6. [Factor 6: Launch/Pause/Resume with simple APIs](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-06-launch-pause-resume.md)
7. [Factor 7: Contact humans with tool calls](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-07-contact-humans-with-tools.md)
8. [Factor 8: Own your control flow](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-08-own-your-control-flow.md)
9. [Factor 9: Compact Errors into Context Window](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-09-compact-errors.md)
10. [Factor 10: Small, Focused Agents](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-10-small-focused-agents.md)
11. [Factor 11: Trigger from anywhere, meet users where they are](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-11-trigger-from-anywhere.md)
12. [Factor 12: Make your agent a stateless reducer](https://github.com/humanlayer/12-factor-agents/blob/main/content/factor-12-stateless-reducer.md)

**Honorable Mention:**
- [Factor 13: Pre-fetch all the context you might need](https://github.com/humanlayer/12-factor-agents/blob/main/content/appendix-13-pre-fetch.md)

---

## How We Got Here

### Software as a Directed Graph

Software is a directed graph. There's a reason we used to represent programs as flow charts.

Around 20 years ago, DAG orchestrators became popular — Airflow, Prefect, Dagster, Inngest, Windmill. These followed the same graph pattern with added observability, modularity, retries, and administration.

### The Promise of Agents

The biggest takeaway when learning about agents: you get to throw the DAG away. Instead of software engineers coding each step and edge case, you give the agent a goal and a set of transitions — and let the LLM make decisions in real time to figure out the path.

The promise: write less software. Give the LLM the "edges" of the graph and let it figure out the nodes. Recover from errors, write less code, and let LLMs find novel solutions.

### Agents as Loops

It turns out this doesn't quite work.

The agent loop consists of:

1. LLM determines the next step in the workflow, outputting structured JSON ("tool calling")
2. Deterministic code executes the tool call
3. The result is appended to the context window
4. Repeat until the next step is determined to be "done"

```python
initial_event = {"message": "..."}
context = [initial_event]
while True:
  next_step = await llm.determine_next_step(context)
  context.append(next_step)

  if (next_step.intent === "done"):
    return next_step.final_answer

  result = await execute_step(next_step)
  context.append(result)
```

The initial context is just the starting event (user message, cron, webhook, etc.), and the LLM chooses the next step (tool) or determines it's done.

---

## Why 12-Factor Agents?

At the end of the day, the "prompt + tools + loop" approach just doesn't work as well as we want it to.

In building HumanLayer, I've talked to at least 100 SaaS builders (mostly technical founders) looking to make their existing product more agentic. The journey usually goes:

1. Decide you want to build an agent
2. Product design, UX mapping, what problems to solve
3. Want to move fast, so grab $FRAMEWORK and get to building
4. Get to 70–80% quality bar
5. Realize that 80% isn't good enough for most customer-facing features
6. Realize that getting past 80% requires reverse-engineering the framework, prompts, flow, etc.
7. Start over from scratch

### Design Principles for Great LLM Applications

After digging through hundreds of AI libraries and working with dozens of founders:

1. There are some core things that make agents great
2. Going all in on a framework and building what is essentially a greenfield rewrite may be counter-productive
3. There are some core principles that make agents great, and you will get most/all of them if you pull in a framework
4. BUT, the fastest way to get high-quality AI software in the hands of customers is to take small, modular concepts from agent building, and incorporate them into your existing product
5. These modular concepts can be defined and applied by most skilled software engineers, even without an AI background

> **The fastest way I've seen for builders to get good AI software in the hands of customers is to take small, modular concepts from agent building, and incorporate them into their existing product.**

---

## Related Resources

- [12 Factor Apps](https://12factor.net) — the original inspiration
- [Building Effective Agents (Anthropic)](https://www.anthropic.com/engineering/building-effective-agents#agents)
- [The Outer Loop (Dex's newsletter)](https://theouterloop.substack.com)
- [Tool Use podcast episode](https://youtu.be/8bIHcttkOTE) — March 2025
- [got-agents/agents](https://github.com/got-agents/agents) — OSS agents built with this methodology
- [kubechain](https://github.com/humanlayer/kubechain) — framework for distributed agents in Kubernetes
- [Library patterns: Why frameworks are evil](https://tomasp.net/blog/2015/library-frameworks/)
- [The Wrong Abstraction](https://sandimetz.com/blog/2016/1/20/the-wrong-abstraction)
- [The AI Agent Index (MIT)](https://aiagentindex.mit.edu/)
- DAG orchestrators: [Airflow](https://airflow.apache.org/), [Prefect](https://www.prefect.io/), [Dagster](https://dagster.io/), [Inngest](https://www.inngest.com/), [Windmill](https://www.windmill.dev/)

---

## License

Content and images: CC BY-SA 4.0
Code: Apache 2.0
