---
title: Private To Public Note Derivation
summary: A sanitized example of converting internal operational knowledge into a public-safe architecture note.
status: reviewed
visibility: public
derived_from: task-0021
redaction_status: reviewed_clean
tags:
  - public-memory
  - case-study
  - publishing
  - redaction
---

# Private To Public Note Derivation

## Why It Matters

It is often easier to talk about a publishable memory layer in theory than to show what “derived from private memory” actually means in practice.

## Public-Safe Summary

A good public note usually starts from a private operational note, decision, or prompt. The public version keeps the lesson and removes the internals.

For example, a private note might describe:

- specific host or network details
- exact filesystem paths
- internal workflows tied to a private environment
- operational caveats meaningful only inside one deployment

A public derivative should keep only the reusable pattern:

- why the architecture exists
- what problem it solves
- how the workflow works in general
- what boundaries keep it safe and maintainable

## Example Pattern

Private source material:

- detailed operational decision about where canonical memory lives
- internal notes about how multiple tools access that memory
- repo-specific setup instructions

Public derivative:

- "Use a versioned, human-readable memory layer outside chat history"
- "Treat publishable notes as derived from private canonical memory"
- "Use scoped retrieval and proposal-first updates to reduce drift"

## What Gets Removed

- exact internal paths when generic examples are enough
- live hostnames, IPs, credentials, and service details
- raw logs, screenshots, exports, and transcripts
- internal-only troubleshooting detail that is not necessary for the public lesson

## What Stays

- the core architecture decision
- the workflow pattern
- the safety boundaries
- the practical lessons others can reuse

## Boundaries

- A sanitized case study should teach a pattern, not reconstruct the private environment.
- If the lesson only makes sense with private detail intact, it may not be a strong public candidate yet.

## Follow-Up

- See `../workflows/private-to-public-publishing-flow.md`
- See `../workflows/public-redaction-review-checklist.md`
- See `../decisions/public-memory-as-derived-layer.md`
