---
name: pr-description
description: >-
  Agent-only PR-description template for every ship task.
  Use when writing or updating a PR body, right before opening the PR.
  This skill is the single owner of the fixed three-section shape - Why, What changed, Validation and proof - and how to fill each section well: short bullets, not prose paragraphs.
user-invocable: false
metadata:
  internal: true
---

# pr-description

This skill is the single owner of firstmate's PR-description template.
`bin/fm-dod-lib.sh` points every ship brief here at the PR-writing step; it does not restate this template.
Write the PR body in exactly these three sections, in this order, whichever project it lands in.
Every section is short bullets, not prose paragraphs - a couple of lines per bullet at most, and never restate context the reviewer can already see in the diff.

## Why

- One or two bullets on the concrete problem this PR solves, not what you did to solve it.
- Name the failure, missing capability, or request that motivated the change; if it traces to a filed issue, say so in the same bullet.
- Never name the requester, describe the change as following an instruction, or use any firstmate-internal terms (captain, firstmate, crewmate, ship, brief, worker, and the like) - state the motivation as a plain fact about the project.
- Skip a "why" that only restates the title - keep looking for the actual motivation instead.

## What changed

- One bullet per fact a reviewer can check directly against the diff, ordered by what they'd want to see first.
- Call out anything intentionally left unchanged - a related-looking case, a known limitation, a deferred follow-up - so it doesn't read as missed.
- No bullets for exploration path, dead ends, or intermediate approaches - only what landed.

## Validation and proof

A checklist, not prose:

- [ ] Focused tests pass covering the change.
- [ ] Existing control behavior is still covered (the change did not silently break what already worked).
- [ ] UI proof is attached when the change is user-visible (screenshot, recording, or artifact link).
- [ ] A fresh reviewer or agent reviewed the diff.

- Check only the boxes actually satisfied; leave a box unchecked with a one-line reason rather than deleting it or checking it speculatively.
- Link the actual evidence behind each checked box (test command and result, screenshot, review output) - a checkmark alone is not proof.
