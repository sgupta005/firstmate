---
name: pr-description
description: >-
  Agent-only PR-description template for every ship task.
  Use when writing or updating a PR body, right before opening the PR.
  This skill is the single owner of the fixed three-section shape - Why, What changed, Validation and proof - and how to fill each section well, not just a restatement of the checkbox labels.
user-invocable: false
metadata:
  internal: true
---

# pr-description

This skill is the single owner of firstmate's PR-description template.
`bin/fm-brief.sh` points every ship brief here at the PR-writing step; it does not restate this template.
Write the PR body in exactly these three sections, in this order, whichever project it lands in.

## Why

State the problem this PR solves, not what you did to solve it.
Name the concrete failure, missing capability, or request that motivated the change; if it traces to a captain instruction or a filed issue, say so in one clause.
One or two sentences is normally enough.
A "why" that just restates the title or repeats the first bullet of "What changed" is not a why - keep looking for the actual motivation until you find it.

## What changed

Bullet the smallest useful change: each bullet should be one fact a reviewer can check directly against the diff.
Order bullets by what a reviewer would want to see first, not by the order you wrote the code.
Explicitly call out anything intentionally left unchanged - a related-looking case, a known limitation, a follow-up deferred on purpose - so a reviewer does not have to guess whether it was missed.
Do not narrate the exploration path, dead ends, or intermediate approaches; state only what landed.

## Validation and proof

A checklist, not prose:

- [ ] Focused tests pass covering the change.
- [ ] Existing control behavior is still covered (the change did not silently break what already worked).
- [ ] UI proof is attached when the change is user-visible (screenshot, recording, or artifact link).
- [ ] A fresh reviewer or agent reviewed the diff.

Check only the boxes actually satisfied.
Leave a box unchecked with a one-line reason - never delete it or check it speculatively - when it genuinely does not apply (e.g. no UI surface changed) or was not done.
Link the actual evidence behind each checked box (the test command and result, the screenshot, the review output) rather than treating the checkmark alone as proof.

## Filling it well

Write "Why" from the reader's perspective (the captain, a future maintainer), not the implementation's.
Keep "What changed" bullets factual and independently verifiable from the diff; drop a bullet you cannot point to a concrete change for.
Treat "Validation and proof" as the evidence a fresh reviewer would need to trust the change without re-doing your work, not a formality to complete.
