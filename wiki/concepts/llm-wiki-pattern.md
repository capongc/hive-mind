---
tags: [llm-wiki, knowledge-management, rag, obsidian, pattern, compounding-knowledge]
sources: [adrej-karpathy-llmwiki.md]
created: 2026-04-18
updated: 2026-04-18
---

# LLM Wiki Pattern

A knowledge management pattern in which an LLM incrementally builds and maintains a persistent, interlinked wiki — rather than re-deriving knowledge from raw sources on every query (the RAG approach). Described by [[Andrej Karpathy]]. This vault is an implementation of this pattern.

## The Key Distinction from RAG

**RAG:** raw documents → retrieve chunks at query time → generate answer → nothing persists  
**LLM Wiki:** raw documents → LLM compiles into wiki → wiki is the persistent knowledge artifact → queries synthesize from the wiki

With RAG, the LLM rediscovers knowledge from scratch on every question. With the wiki pattern, knowledge compounds: cross-references are already built, contradictions already flagged, synthesis already reflects everything read.

> "The wiki is a persistent, compounding artifact."

## Three-Layer Architecture

| Layer | Description | Who Owns It |
|---|---|---|
| **raw/** | Immutable source documents (articles, papers, notes) | Human |
| **wiki/** | Structured, interlinked markdown pages | LLM |
| **schema** | CLAUDE.md / AGENTS.md — wiki conventions and workflows | Human + LLM co-evolve |

## Three Core Operations

- **Ingest** — LLM reads a new source, discusses takeaways, writes a summary page, updates index + entity/concept pages, appends to log. One source may touch 10–15 wiki pages.
- **Query** — LLM reads the index, drills into relevant pages, synthesizes answer with citations. Valuable answers get filed back as synthesis pages — explorations compound too.
- **Lint** — periodic health check: contradictions, stale claims, orphan pages, missing cross-references, data gaps.

## Why It Works

The tedious part of maintaining a knowledge base is the bookkeeping — updating cross-references, noting contradictions, keeping summaries current. Humans abandon wikis because maintenance burden grows faster than value. LLMs don't get bored or forget cross-references; they can touch 15 files in one pass. Maintenance cost approaches zero.

> "The human's job is to curate sources, direct the analysis, ask good questions, and think about what it all means. The LLM's job is everything else."

## Historical Reference

Spiritually related to Vannevar Bush's **Memex** (1945) — a personal, curated knowledge store with associative trails between documents. Bush's vision was closer to this than to what the web became: private, actively curated, with connections as valuable as the documents themselves. The unsolved part was: *who does the maintenance?* The LLM handles that.

## Related

- [[Andrej Karpathy]]
- [[Human-in-the-Loop]]
- [[Agent Swarm]]
