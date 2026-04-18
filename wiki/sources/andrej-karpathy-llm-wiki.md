---
tags: [llm-wiki, knowledge-management, rag, obsidian, pattern]
sources: [adrej-karpathy-llmwiki.md]
created: 2026-04-18
updated: 2026-04-18
---

# Andrej Karpathy — LLM Wiki Pattern

**Source:** raw/assets/adrej-karpathy-llmwiki.md
**Date ingested:** 2026-04-18
**Type:** idea document / pattern

## Summary

Describes the foundational pattern behind this vault — LLMs incrementally build and maintain a persistent, interlinked wiki rather than re-deriving knowledge from raw sources on every query (the RAG approach). Authored by [[Andrej Karpathy]]. The human curates and directs; the LLM does all the maintenance bookkeeping.

## Key Claims

- RAG re-discovers knowledge from scratch on every question — nothing accumulates; the LLM wiki pattern compiles knowledge once and keeps it current
- The wiki is a persistent, compounding artifact — cross-references already exist, contradictions already flagged, synthesis already reflects everything read
- A single source ingest may touch 10–15 wiki pages — this is expected and normal
- Good query answers should be filed back into the wiki as synthesis pages — explorations compound just like ingested sources
- The human's job: source curation, direction, asking good questions. The LLM's job: everything else
- LLMs don't get bored or forget to update a cross-reference — they can touch 15 files in one pass; maintenance cost is near zero
- Spiritually related to Vannevar Bush's Memex (1945) — the part Bush couldn't solve (who does the maintenance) is now handled by the LLM

## Three-Layer Architecture

- **Raw sources** — immutable source documents; LLM reads but never modifies
- **Wiki** — LLM-generated markdown files; LLM owns this layer entirely
- **Schema** — CLAUDE.md / AGENTS.md; tells the LLM how the wiki is structured and what workflows to follow

## Operations

- **Ingest:** drop source into raw/, LLM reads, discusses takeaways, writes summary, updates index and entity/concept pages, appends to log
- **Query:** LLM reads index, drills into relevant pages, synthesizes answer with citations; valuable answers filed back as synthesis pages
- **Lint:** periodic health check — contradictions, stale claims, orphan pages, missing cross-references, data gaps

## Tooling Mentioned

- **Obsidian** — the IDE for viewing the wiki in real time
- **Obsidian Web Clipper** — browser extension to convert web articles to markdown for raw/
- **qmd** — local search engine for markdown with hybrid BM25/vector search and LLM re-ranking
- **Marp** — markdown-based slide deck format
- **Dataview** — Obsidian plugin for querying page frontmatter

## Entities Mentioned

- [[Andrej Karpathy]] — author of this pattern document

## Concepts Covered

- [[LLM Wiki Pattern]] — primary concept; the foundational pattern of this vault
- [[Human-in-the-Loop]] — human curates and directs; LLM executes maintenance
