---
title: Public Agent Install And Config
summary: A public-safe workflow for connecting an outside AI tool to the public-memory layer as a scoped knowledge base.
status: reviewed
visibility: public
derived_from: task-0021
redaction_status: reviewed_clean
tags:
  - public-memory
  - workflow
  - installation
  - configuration
  - ai-agent
---

# Public Agent Install And Config

## Why It Matters

A public-memory layer is only useful if an outside agent can be connected to it quickly and safely. Clear setup guidance helps avoid two common mistakes: treating the public layer like private operational memory, or giving the tool broader filesystem access than it needs.

## Public-Safe Summary

Install and configure outside agents against the public-memory layer by granting the smallest access that still lets them answer useful questions. In most cases, that means pointing the agent at `public-memory/`, having it read the orientation notes first, and restricting any indexing or retrieval to that folder alone.

## Workflow

1. Obtain the published `public-memory/` folder or repository snapshot.
2. Mount, open, or upload only that public-memory content.
3. Read `context-manifest.yaml`, `README.md`, and `AGENTS.md` before task-specific notes.
4. Use the manifest's authoritative files and task routing to select the smallest relevant bundle.
5. Configure retrieval to search inside `architecture/`, `workflows/`, `decisions/`, `prompts/`, and `templates/` only when the manifest does not already name the needed note.
6. Confirm the agent understands that public memory is derived and incomplete by design.
7. Use scoped retrieval during work instead of loading the whole corpus into a prompt.
8. If a task requires private operational context, pause and request the correct private source explicitly.

## Minimal Setup Checklist

- The agent can access `public-memory/`.
- The agent reads `context-manifest.yaml` before selecting supporting notes.
- The agent reads `README.md`.
- The agent reads `AGENTS.md`.
- The agent knows which subfolders to search first.
- The agent is not configured to crawl unrelated private folders by default.
- The operator understands that public updates should be rewritten for publication, not copied directly from private memory.

## Configuration Patterns

### Local Repo Or Folder Access

- Clone or copy the public-memory layer into a workspace the agent can read.
- Set the working scope to `public-memory/`.
- Disable broad sibling-folder indexing unless it is explicitly needed for another task.

### Search Or Embedding Setup

- Build the index from `public-memory/` only.
- Keep filenames, headings, and frontmatter available to the retrieval layer when possible.
- Refresh the index when published notes change.

### Task-Level Context Manifests

- Start with the repository `context-manifest.yaml` as the default packet.
- For a repeated project or task, create a small manifest from `templates/context-manifest-template.yaml`.
- Point at canonical public notes rather than duplicating their contents in the manifest.
- Include authoritative files, allowed edit scope, known unknowns, and explicit non-inference rules.

### Chat Tool With File Uploads

- Upload `README.md` and `AGENTS.md` first.
- Add the smallest set of supporting notes needed for the task.
- Re-upload updated notes when the published layer changes materially.

## Validation

After setup, the agent should be able to:

- explain the scope of the public-memory layer
- identify that private memory remains canonical elsewhere
- answer questions from the published notes without inventing hidden context
- say clearly when a requested answer depends on unavailable private information

## Boundaries

- Do not point outside agents at raw imports, logs, screenshots, or secret-bearing operational material.
- Do not treat public-memory installation as permission to write back into private canonical memory.
- Do not promise exact infrastructure behavior from a sanitized public note set.

## Follow-Up

- See `../architecture/public-memory-access-patterns.md`
- See `../decisions/public-memory-as-derived-layer.md`
- See `../prompts/public-shared-memory-onboarding.md`
