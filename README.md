# Public Memory

This repository documents a shared AI memory layer: a Markdown-and-Git knowledge base designed so multiple AI assistants can reuse durable context across coding, operations, and documentation sessions instead of starting from scratch every time.

It is meant for people building multi-agent or multi-tool workflows and for AI agents that need a small, inspectable, human-reviewable memory surface rather than a giant chat transcript dump.

This repository is the public-safe derivative of a private shared-memory system. The private canonical source of truth stays elsewhere; the material here is rewritten and reviewed for publication.

`Nemotron` in the repo name is historical project naming from earlier orchestration work. This repository is not specific to NVIDIA Nemotron and does not require any particular model family.

## Purpose

Use this layer to publish architecture, workflows, prompts, patterns, and lessons learned without exposing private infrastructure details, client-sensitive material, raw imports, or internal operations data.

## How It Works

At a high level, the system works like this:

1. Durable project knowledge is kept in a private Markdown-and-Git memory system.
2. Public-safe parts are rewritten as derivative notes instead of copied directly.
3. Those rewritten notes are reviewed for clarity and redaction.
4. The reviewed public notes are published here as a smaller knowledge base that humans and AI agents can read directly.

In practice, that means this repository is not a raw export or a full private vault mirror. It is a curated public layer: compact enough to browse, structured enough to retrieve from, and explicit enough for both humans and AI tools to inspect.

For actual use, the expected read path is:

- start with `context-manifest.yaml` for the machine-readable default context and non-inference rules
- read `README.md` for scope and boundaries
- use `index.md` to find the relevant note set
- read only the architecture or workflow note routed to the task instead of loading the whole repo
- use `AGENTS.md` when an AI tool needs mounting, indexing, or retrieval guidance

The manifest is a retrieval contract, not a second knowledge base. It points to
the reviewed notes that are authoritative for this public layer, records known
unknowns, and makes the boundaries explicit before an agent starts reasoning.

## Start Here

If you want one concrete entry point instead of browsing blind:

- Read `architecture/shared-memory-foundation.md` for the core model.
- Read `context-manifest.yaml` for the default AI context packet.
- Read `workflows/public-agent-install-and-config.md` for how an agent should mount and use this repo.
- Read `case-studies/scoped-retrieval-in-practice.md` for a practical example of scoped retrieval instead of loading everything.
- Use `index.md` for a guided map of the repo.

## Design Rules

- Private memory stays canonical.
- Public memory is derived and reviewable.
- Public memory is authored and updated from the private shared-memory repo, then published outward from there.
- Public notes should be rewritten for publication, not copied verbatim from private notes.
- Public memory should be useful to outside humans and AI agents without requiring access to the private system.
- Sensitive paths, usernames, IPs, hostnames, screenshots, logs, tokens, and credentials must be removed or generalized.

## What's In Here

- `architecture/` - design notes explaining the memory model, access patterns, and scoped retrieval approach.
- `workflows/` - operational guides for proposal-first updates, agent setup, redaction review, and private-to-public publishing.
- `prompts/` - reusable onboarding prompt material for agents using this repo as memory.
- `decisions/` - compact rationale for key design choices behind the public layer.
- `case-studies/` - concrete examples showing how the patterns were applied in practice.
- `templates/` - starter structure for authoring additional public-safe notes.
- `context-manifest.yaml` - machine-readable default context, retrieval routing, and explicit non-inference boundaries.

## Layout

```text
repo root
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

An outside AI agent should be able to use this repository as a self-contained public knowledge base. In practice, the short path is:

- read `README.md`
- use `index.md` as the navigation map
- read `AGENTS.md` for mounting, indexing, and retrieval guidance

The agent should not assume access to any private repo or hidden operational context unless the user explicitly provides it.

## License

This layer is published under the Creative Commons Attribution 4.0 International License (CC BY 4.0). See `LICENSE.md` for the full text. For feedback or corrections, see `CONTRIBUTING.md`.
