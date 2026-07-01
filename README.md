# Public Memory

This is part of a personal system for giving multiple AI assistants a shared, durable, human-reviewable memory, so context can persist across tools and sessions instead of being re-explained in every conversation. This folder is the publishable, sanitized derivative of that system's private memory.

This folder is a prototype for a public-facing memory layer. It is not the private source of truth. The canonical internal memory remains under `memory/`.

## Purpose

Use this layer to publish architecture, workflows, prompts, patterns, and lessons learned without exposing private infrastructure details, client-sensitive material, raw imports, or internal operations data.

## Design Rules

- Private memory stays canonical.
- Public memory is derived and reviewable.
- Public memory is authored and updated from the private shared-memory repo, then published outward from there.
- Public notes should be rewritten for publication, not copied verbatim from private notes.
- Public memory should be useful to outside humans and AI agents without requiring access to the private repo.
- Sensitive paths, usernames, IPs, hostnames, screenshots, logs, tokens, and credentials must be removed or generalized.

## Recommended Layout

```text
public-memory/
  README.md
  AGENTS.md
  architecture/
  workflows/
  prompts/
  decisions/
  case-studies/
  templates/
```

## Good Public Candidates

- shared-memory architecture
- proposal-first workflow
- AI bootstrap patterns
- retrieval and context-bundle design
- prompt and handoff patterns
- generalized lessons learned from multi-tool coordination

## Keep Private

- real internal paths where they create unnecessary exposure
- real IP addresses and hostnames
- client/project-sensitive information
- screenshots, logs, exports, and raw transcripts
- credentials, tokens, keys, cookies, and auth details
- operational weaknesses or attack-surface details that are not necessary for the public explanation

## Publishing Model

The intended flow is:

1. Create or update private canonical memory.
2. Identify a public-safe derivative.
3. Rewrite it for publication.
4. Review for redaction and clarity.
5. Publish from this layer or a separate public repo built from this layer.

## AI Use

An outside AI agent should be able to use this folder as a self-contained public knowledge base. See `AGENTS.md` for installation, mounting, indexing, and usage guidance.

## License

This layer is published under the Creative Commons Attribution 4.0 International License (CC BY 4.0). See `LICENSE.md` for the full text. For feedback or corrections, see `CONTRIBUTING.md`.
