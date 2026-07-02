---
title: Public Memory Index
summary: A browsable map of the publishable shared-memory layer.
status: reviewed
visibility: public
derived_from: task-0021
redaction_status: reviewed_clean
tags:
  - public-memory
  - index
  - navigation
---

# Public Memory Index

## Purpose

This index helps humans and AI agents navigate the public-memory layer without having to infer structure from the folder tree alone.

## Start Here

- `README.md` - what this repository is, who it is for, and where to begin
- `AGENTS.md` - how an AI agent should mount, index, and query the repo safely
- `LICENSE.md` - publication license
- `CONTRIBUTING.md` - feedback and correction path
- `prompts/public-shared-memory-onboarding.md` - reusable onboarding prompt for agents

## Architecture

- `architecture/shared-memory-foundation.md` - the core mental model for durable shared memory
- `architecture/public-memory-access-patterns.md` - patterns for reading and exposing memory safely
- `architecture/scoped-context-bundles.md` - why retrieval should be narrow instead of loading everything

## Workflows

- `workflows/proposal-first-memory-updates.md` - how updates stay reviewable before canonical promotion
- `workflows/public-agent-install-and-config.md` - setup guidance for AI tools using this repo directly
- `workflows/public-redaction-review-checklist.md` - review rules for removing sensitive detail
- `workflows/private-to-public-publishing-flow.md` - how private notes become public-safe derivatives

## Decisions

- `decisions/public-memory-as-derived-layer.md` - why the public layer is derived instead of canonical

## Case Studies

- `case-studies/README.md` - folder overview
- `case-studies/private-to-public-note-derivation.md` - example of rewriting a private note into a public-safe artifact
- `case-studies/scoped-retrieval-in-practice.md` - example of using scoped context instead of broad memory loading

## Templates

- `templates/public-note-template.md` - starter structure for authoring new public notes

## Reading Order

1. Read the public scope and boundaries.
2. Read one architecture note to understand the model.
3. Read one workflow note for practical operation.
4. Use the prompt or template only when applying the pattern.
