---
name: kuma-core-invariants
description: "Use when reviewing architecture, refactors, state/data ownership, duplication, code and test structure, failure handling, debug discipline, work-in-progress hygiene, or concurrency policy against Alex's eight fixed invariants."
---

# Kuma Core Invariants Skill

## Source of Truth

- Canonical policy text lives in `README.md`; on any drift with this file, README.md wins.
- Link to `README.md`; never copy the invariants into another file.

## Workflow

1. Read `README.md` first.
2. Recommend the smallest change that restores the invariant boundary.

## Output Expectations

- Findings first when doing review work.
- Name the invariant, or the Simplicity rule, being violated.
- Prefer fixes that remove structure — duplicates, unneeded guards and tests, legacy, ownership overlap, hidden recovery logic — over fixes that add it.
- For a taxonomy finding, name the branch the unit belongs on.
- Call out explicit failover separately from silent fallback.
- For doc-first violations, cite the exact docs page that already had the answer.
