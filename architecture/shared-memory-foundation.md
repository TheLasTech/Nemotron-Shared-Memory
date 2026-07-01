---
title: Shared Memory Foundation
summary: A practical pattern for giving multiple AI tools a durable, reviewable source of truth outside any single chat thread.
status: reviewed
visibility: public
derived_from: decision-0001
redaction_status: reviewed_clean
tags:
  - public-memory
  - architecture
  - shared-context
  - ai-tools
---

# Shared Memory Foundation

## Why It Matters

Most AI tools are good at short-term reasoning but weak at carrying reliable context across many sessions, tools, and projects. A shared-memory layer solves that by moving durable knowledge out of chat history and into reviewable files.

## Public-Safe Summary

The core pattern is to use plain-text notes in a versioned repository as the durable source of truth for long-lived context. That memory can then be read by multiple AI tools, humans, and automation systems without forcing any one chat thread to carry everything.

In this design, Markdown is used because it is portable and easy to inspect. Git is used because it provides history, diffs, rollback, and synchronization. Human review remains important so the memory stays coherent instead of turning into an uncurated pile of transcripts.

## Pattern

- Keep durable knowledge in human-readable notes rather than only inside chat history.
- Version the memory so changes can be reviewed and rolled back.
- Store summaries, decisions, tasks, and stable facts instead of relying on raw transcripts as default context.
- Let tools retrieve only the relevant memory for a task rather than loading everything at once.

## Boundaries

- This pattern does not require exposing private infrastructure details.
- Raw transcripts, sensitive logs, and credentials should not be treated as general-purpose memory.

## Follow-Up

- See `../workflows/proposal-first-memory-updates.md`
- See `../decisions/public-memory-as-derived-layer.md`
