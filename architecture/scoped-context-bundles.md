---
title: Scoped Context Bundles
summary: A retrieval pattern that gives AI tools only the context needed for the current task instead of a giant handoff.
status: reviewed
visibility: public
derived_from: decision-0002
redaction_status: reviewed_clean
tags:
  - public-memory
  - architecture
  - retrieval
  - context
---

# Scoped Context Bundles

## Why It Matters

One of the fastest ways to waste tokens and confuse an AI system is to load a huge project history when only a narrow slice is needed.

## Public-Safe Summary

Scoped context bundles are small, focused sets of notes assembled for a specific task. Instead of giving an agent every document, transcript, and decision, you give it only the pieces relevant to the current objective.

This keeps retrieval cheaper, makes the reasoning trace easier to understand, and reduces the chance that stale or irrelevant material dominates the task.

## Pattern

- Break large work into smaller tasks.
- Retrieve only the notes relevant to the current task.
- Prefer decisions, summaries, tasks, and stable system notes over raw transcripts.
- Keep provenance visible so the agent can tell where a fact came from.
- Ask for more context only when the current bundle is insufficient.

## Benefits

- lower token pressure
- clearer reasoning inputs
- less contamination from stale context
- easier review of what the agent actually used

## Boundaries

- A scoped bundle is not a replacement for durable memory.
- If the scope is too narrow, important constraints can still be missed.
- Full transcripts may still be useful for deep dives, but should not be the default context surface.

## Follow-Up

- See `shared-memory-foundation.md`
- See `public-memory-access-patterns.md`
