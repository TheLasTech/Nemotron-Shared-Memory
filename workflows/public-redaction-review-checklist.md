---
title: Public Redaction Review Checklist
summary: A lightweight checklist for reviewing whether a note is safe to publish from a private memory system into a public derivative layer.
status: reviewed
visibility: public
derived_from: task-0021
redaction_status: reviewed_clean
tags:
  - public-memory
  - workflow
  - redaction
  - publishing
---

# Public Redaction Review Checklist

## Why It Matters

Publishing useful notes is easier than publishing safe notes. A redaction review step helps catch the details that feel ordinary inside a private system but create unnecessary exposure in a public artifact.

## Public-Safe Summary

Before a note moves into a public memory layer, review it as if the audience has no trusted background context. The goal is not only to remove secrets, but also to remove operational details, identifiers, and accidental clues that make private systems more legible than they need to be.

This checklist works best when the public note is rewritten for publication instead of copied directly from private memory.

## Checklist

- Remove credentials, tokens, keys, cookies, and auth material.
- Remove real usernames, personal identifiers, client names, and sensitive project names unless they are explicitly intended for publication.
- Replace internal filesystem paths with generic examples when the exact path is not important to the lesson.
- Remove or generalize IP addresses, hostnames, internal URLs, service names, and network topology details.
- Remove screenshots, logs, raw transcripts, exports, and stack traces unless they have been intentionally sanitized and are necessary for the explanation.
- Remove operational weaknesses, failure modes, or exposed surfaces that are not required for the public lesson.
- Check metadata, frontmatter, examples, and follow-up links for private references that remain after the main text is rewritten.
- Rewrite language that assumes private context so the note still makes sense on its own.
- Confirm the note teaches a reusable pattern, decision, or workflow rather than documenting internal state.
- Do a final read as an outside reviewer and ask: "Would publishing this reveal more than the lesson requires?"

## Boundaries

- Redaction is not only about secrets. General operational detail can also be sensitive.
- If a note needs extensive private detail to remain useful, it may not be a good public candidate.

## Follow-Up

- See `../workflows/private-to-public-publishing-flow.md`
- See `../decisions/public-memory-as-derived-layer.md`
