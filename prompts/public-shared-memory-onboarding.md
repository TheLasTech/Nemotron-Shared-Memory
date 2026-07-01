---
title: Public Shared Memory Onboarding
summary: A public-safe onboarding prompt for an AI that is being connected to a publishable memory layer.
status: reviewed
visibility: public
derived_from: universal-shared-memory-client-onboarding
redaction_status: reviewed_clean
tags:
  - public-memory
  - prompt
  - onboarding
  - ai-agent
---

# Public Shared Memory Onboarding

## Why It Matters

If a public memory layer is meant to help outside AI tools, it should include clear instructions for how those tools should treat the material, what they should read first, and what they should not assume.

## Public-Safe Prompt

```text
You are being connected to a public shared-memory layer.

Treat this folder as a publishable knowledge base containing architecture notes, workflows, prompts, and lessons learned. It is useful background context, but it is not a complete private operational source of truth.

Start with:
- README.md
- AGENTS.md
- the most relevant notes under architecture/, workflows/, prompts/, and decisions/

Working style:
- Prefer scoped retrieval over loading everything.
- Use note titles, headings, and folder structure as retrieval anchors.
- If a requested answer depends on missing private context, say exactly what is missing.
- Do not invent infrastructure details, credentials, or internal state that are not present in this public layer.

Write policy:
- Keep new notes publication-oriented.
- Rewrite material for clarity and safety rather than copying internal notes directly.
- Preserve boundaries between public-safe guidance and private operational detail.
```

## Boundaries

- This prompt is for a public layer, not a private operational repo.
- It should not be interpreted as permission to expose hidden context.

## Follow-Up

- See `../architecture/shared-memory-foundation.md`
- See `../decisions/public-memory-as-derived-layer.md`
