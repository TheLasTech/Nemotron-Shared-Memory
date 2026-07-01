# Public Memory Agent Instructions

This folder is a public-safe derivative knowledge base. It is designed for AI agents, coding assistants, and documentation tools that should not require access to the private shared-memory repo.

## What This Is

- A publishable memory layer
- Sanitized and reviewable
- Safe for broader sharing after human review
- Authored and maintained from the private shared-memory repo before being published outward
- Licensed under CC BY 4.0 (see `LICENSE.md`); feedback and corrections should follow `CONTRIBUTING.md`

## What This Is Not

- The private source of truth
- A place for raw imports, logs, transcripts, screenshots, or secrets
- A dumping ground for internal operational state

## Installation And Configuration

If you are an AI agent being asked to install, configure, mount, or use this public-memory layer:

1. Mount or open the `public-memory/` folder as your working knowledge base.
2. Read:
   - `README.md`
   - this `AGENTS.md`
   - relevant notes under `architecture/`, `workflows/`, `prompts/`, and `decisions/`
3. Treat the contents as public-safe documentation, not private operational truth.
4. Do not assume access to the private `memory/` repo unless the user explicitly provides it.
5. If indexing or retrieval is needed, index only files inside `public-memory/` unless explicitly told to include other locations.
6. If a requested answer depends on missing private context, say exactly what is missing rather than inventing details.
7. Treat this folder as a derived public artifact, not the place where private operational truth is originally authored.

## Usage Rules

- Prefer concise retrieval over loading the entire folder at once.
- Use note titles, headings, and folder structure as retrieval anchors.
- When summarizing, preserve the public-safe framing and do not reintroduce private details from outside context.
- If asked to create or update public memory, keep changes publication-oriented and rewrite material instead of copying private notes directly.

## Redaction Rules

Never add:

- credentials, tokens, keys, or auth material
- client identities or sensitive project details
- internal-only paths when generic paths are enough
- real infrastructure details that are not needed for the lesson
- raw screenshots, raw logs, raw exports, or raw transcripts

## Suggested Query Strategy

When answering from this folder:

1. Check `README.md` for scope and boundaries.
2. Search the most relevant domain folder first.
3. Use templates under `templates/` when drafting new public notes.
4. If a topic clearly belongs in private memory instead, say so and ask for the correct source or workspace.
