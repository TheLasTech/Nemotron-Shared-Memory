---
title: Public Memory Access Patterns
summary: Safe, reusable ways for outside AI tools to read, index, and retrieve from a publishable memory layer without assuming private access.
status: reviewed
visibility: public
derived_from: task-0021
redaction_status: reviewed_clean
tags:
  - public-memory
  - architecture
  - retrieval
  - ai-agent
---

# Public Memory Access Patterns

## Why It Matters

Outside AI tools need a clear way to consume shared context without being pointed at private operational memory. A public-memory layer is most useful when agents know how to access it safely, narrowly, and predictably.

## Public-Safe Summary

The public-memory layer should be treated as a small, publishable knowledge base. Outside tools should start from the public folder itself, read a few orientation files first, and retrieve only the notes relevant to the current task.

This access model keeps context lightweight and reduces the chance that an agent will invent missing private details or treat sanitized notes as a complete operational source of truth.

## Pattern

- Mount or open only the `public-memory/` folder when private memory access is not intended.
- Read orientation notes first: `README.md`, `AGENTS.md`, and the most relevant domain note.
- Retrieve by folder, title, and heading before loading large parts of the corpus.
- Treat architecture, workflows, decisions, prompts, and templates as separate retrieval domains.
- Answer from the public layer as written instead of filling gaps with guessed internal context.
- If a question depends on private details, say what is missing and stop at the public boundary.

## Recommended Access Modes

### Mounted Folder

Use this when an AI tool can read local files or a checked-out repository.

- Point the tool at `public-memory/` instead of the private repo root.
- Keep retrieval scoped to the current topic folder whenever possible.
- Use the local file structure as the primary navigation system.

### Indexed Knowledge Base

Use this when an AI tool works better from search or embeddings than direct file browsing.

- Index only files inside `public-memory/`.
- Preserve note titles and headings because they are useful retrieval anchors.
- Rebuild the index after published note changes instead of mixing private and public corpora.

### Uploaded Document Set

Use this when a tool cannot mount folders or repositories directly.

- Upload the core orientation files first.
- Add only the specific supporting notes needed for the task.
- Prefer small, curated batches over uploading the entire knowledge base by default.

## Retrieval Order

1. Read `README.md` for scope and publishing boundaries.
2. Read `AGENTS.md` for agent behavior and redaction rules.
3. Open the most relevant note under `architecture/`, `workflows/`, `decisions/`, or `prompts/`.
4. Use `templates/` only when drafting new public-safe notes.
5. Stop and ask for more source material if the public layer does not answer the question.

## Boundaries

- Public memory is not the canonical private source of truth.
- Public access should not imply permission to scan neighboring folders or hidden history.
- Sanitized notes should not be treated as evidence for exact internal paths, hosts, credentials, or live operational state.

## Follow-Up

- See `../workflows/public-agent-install-and-config.md`
- See `../workflows/proposal-first-memory-updates.md`
- See `../prompts/public-shared-memory-onboarding.md`
