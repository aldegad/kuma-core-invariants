---
name: alex-core-invariants
description: "Use when reviewing architecture, refactors, state/data ownership, duplication, code and test structure, failure handling, debug discipline, work-in-progress hygiene, or concurrency policy against Alex's eight fixed invariants."
---

# Alex Core Invariants Skill

## Source of Truth

- Canonical policy text lives in `README.md`; on any drift with this file, README.md wins.
- Link to `README.md`; never copy the invariants into another file.

## Workflow

1. Read `README.md` first.
2. Identify the canonical owner for each important truth, and flag copies — duplicated wording, features, or tests.
3. Place each changed unit in the domain taxonomy tree; flag a unit carrying two concerns, and tests that do not sit with the code they cover.
4. Flag dual-write, silent fallback, history-as-canonical, and legacy paths the change touched but kept.
5. For each new guard or test, name the failure only it catches; if there is none, it should not exist. Check that only the tests the change can affect were run.
6. Prefer self-heal from live truth over adding another truth surface.
7. If explicit failover exists, verify that it is observable and does not mutate canonical truth.
8. For problems in a standardized domain, search the official documentation before dispatching hypotheses.
9. Recommend the smallest change that restores the invariant boundary.

## Output Expectations

- Findings first when doing review work.
- Name the invariant, or the Simplicity rule, being violated.
- Prefer fixes that remove structure — duplicates, unneeded guards and tests, legacy, ownership overlap, hidden recovery logic — over fixes that add it.
- For a taxonomy finding, name the branch the unit belongs on.
- Call out explicit failover separately from silent fallback.
- For doc-first violations, cite the exact docs page that already had the answer.
