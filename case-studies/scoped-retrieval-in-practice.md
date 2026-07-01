---
title: Scoped Retrieval In Practice
summary: A walkthrough of an AI tool pulling a small context bundle for one task, drafting a proposal, and having it reviewed before promotion.
status: reviewed
visibility: public
derived_from: task-0021
redaction_status: reviewed_clean
tags:
  - public-memory
  - case-study
  - retrieval
  - proposal-review
---

# Scoped Retrieval In Practice

## Why It Matters

The scoped-context-bundle pattern and the proposal-first workflow are easy to describe abstractly but harder to picture concretely. This note walks through a single, generic-but-representative task end to end, showing what actually got loaded, what got drafted, and what a reviewer did with it.

## Public-Safe Summary

An AI assistant was asked to help resolve a recurring configuration issue on a home server task. Rather than loading the full project history, it retrieved a small bundle: two related task notes describing prior attempts at the same class of problem, and one decision note that had previously settled on a general approach for that category of issue. That bundle was enough context to work from. The assistant drafted a proposed update summarizing the new fix and a refinement to the earlier decision. The proposal was reviewed before anything was written into canonical memory, and only part of it was accepted.

## The Bundle

The retrieval step assembled:

- Task note A: an earlier attempt at a similar problem, including what was tried and why it did not fully resolve things.
- Task note B: a more recent, partially successful attempt at the same category of problem.
- Decision note: a prior decision that set a general policy for how this class of issue should be handled going forward.

Notably absent from the bundle: full chat transcripts, unrelated task notes from other projects, and older superseded notes that had already been folded into the decision note. The assistant did not request those, and did not need them — the three-note bundle contained enough signal to reason about the current task without re-deriving history that had already been settled.

## The Proposal

Working from the bundle, the assistant drafted a proposal rather than editing canonical memory directly. The proposal contained three parts:

1. A summary of the new fix that worked, framed as a candidate update to the relevant task note.
2. A suggested tweak to the existing decision note, generalizing it slightly to cover a variant of the problem the original decision had not anticipated.
3. A flagged uncertainty: the assistant noted it could not confirm whether the fix would hold under a related but untested condition, and suggested this be verified before being treated as settled.

## What Review Looked For

The reviewing human checked the proposal against three questions:

- Does this duplicate something already captured elsewhere in canonical memory?
- Is the suggested generalization actually supported by the evidence in the bundle, or is it overreaching from a single data point?
- Does anything in the proposal need rewording before it becomes durable, reusable memory?

## What Got Promoted vs Rejected

- The fix summary (part 1) was promoted essentially as written into the relevant task note, since it was concrete, verified, and non-duplicative.
- The suggested decision tweak (part 2) was only partially promoted. The reviewer judged the generalization slightly too broad given a single instance of success, and narrowed the wording before merging it into the decision note.
- The flagged uncertainty (part 3) was not promoted into canonical memory at all. Instead it was converted into a new, separate open task so the unresolved question would not get buried inside a decision note that was otherwise meant to be settled.

## Why This Mattered

Because retrieval was scoped rather than exhaustive, the assistant's reasoning stayed traceable — a reviewer could see exactly which three notes informed the proposal, rather than guessing which parts of a much larger context might have influenced it. Because the update went through a proposal step rather than a direct write, an overly broad generalization was caught and narrowed before it became a permanent, load-bearing part of memory that later tasks might have inherited uncritically.

## Boundaries

- This walkthrough is illustrative, not a literal transcript; specifics have been generalized.
- Scoped bundles only work well when the underlying notes are already reasonably well-factored; a messy or duplicated note corpus makes small bundles less reliable.
- Not every proposal needs this much scrutiny — routine, low-risk updates can be reviewed more lightly than a change to a standing decision.

## Follow-Up

- See `../architecture/scoped-context-bundles.md`
- See `../workflows/proposal-first-memory-updates.md`
