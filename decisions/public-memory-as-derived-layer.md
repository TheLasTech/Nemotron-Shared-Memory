---
title: Public Memory Should Be Derived, Not Canonical
summary: A publishable memory layer works best as a sanitized derivative of private canonical memory rather than as a competing source of truth.
status: reviewed
visibility: public
derived_from: task-0021
redaction_status: reviewed_clean
tags:
  - public-memory
  - decision
  - publishing
  - redaction
---

# Public Memory Should Be Derived, Not Canonical

## Why It Matters

When a private knowledge base becomes useful, it is tempting to publish it directly. That usually creates risk because internal memory often contains sensitive paths, operational details, raw context, or assumptions that are safe internally but not suitable for public sharing.

## Public-Safe Summary

A public memory layer should be treated as a reviewed derivative of private memory. The private system remains the source of truth. Public notes are rewritten and sanitized for broader sharing.

This approach preserves clarity:

- private memory stays complete and operational
- public memory stays safe and coherent
- publishing does not force the internal repo to be designed for a public audience first

## Pattern

- Author and maintain canonical knowledge privately.
- Identify public-safe themes and notes.
- Rewrite them for publication.
- Review for redaction, clarity, and reuse value.
- Publish from the derived public layer.

## Boundaries

- Public memory should not become a shadow source of truth that diverges from the private system.
- Public notes should not contain details that are only useful internally.

## Follow-Up

- See `../architecture/shared-memory-foundation.md`
- See `../workflows/proposal-first-memory-updates.md`
