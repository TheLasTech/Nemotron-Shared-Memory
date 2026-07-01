---
title: Proposal-First Memory Updates
summary: A safer workflow for letting AI tools suggest memory changes without silently mutating canonical knowledge.
status: reviewed
visibility: public
derived_from: private-review-workflow
redaction_status: reviewed_clean
tags:
  - public-memory
  - workflow
  - safety
  - ai-writes
---

# Proposal-First Memory Updates

## Why It Matters

AI tools are useful for drafting updates, but direct autonomous edits to long-lived memory can create drift, duplication, or hidden mistakes. A proposal-first workflow preserves speed without giving up review.

## Public-Safe Summary

Instead of allowing every tool to edit canonical memory directly, AI-generated changes first land as reviewable proposals. A human or a trusted reviewing agent then decides whether to promote the useful parts into the real knowledge base.

This keeps the durable memory cleaner and makes it easier to track what was suggested versus what was accepted.

## Pattern

- Write uncertain or automated memory changes as proposals first.
- Review proposals for accuracy, duplication, and sensitivity.
- Promote accepted content into canonical notes.
- Delete, resolve, or archive proposals after promotion.

## Boundaries

- Proposal-first does not eliminate the need for review.
- It should not be used as an excuse to accumulate stale proposal clutter indefinitely.

## Follow-Up

- See `../architecture/shared-memory-foundation.md`
- See `../prompts/public-shared-memory-onboarding.md`
