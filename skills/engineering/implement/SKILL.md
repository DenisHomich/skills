---
name: implement
description: "Implement a piece of work based on a spec or set of tickets."
disable-model-invocation: true
---

Implement the work described by the user in the spec or tickets.

## 1. Run the loop in behaviour-sized cycles

Use `/tdd` at the agreed seams. One cycle covers one behaviour, however many files
that behaviour touches: make all of its edits, one patch per file, then typecheck
and run the test files covering it once.

Re-run a test file when you have changed something it covers. A run that repeats a
pass it already reported spends a round trip to return information you have.

Run the full suite once, at the end.

## 2. Review and commit

Run `/code-review` against the branch point, fix findings, commit to the current
branch.

The gate's completion criterion is checkable and exhaustive: every finding fixed
or accepted in writing, because "fix what comes back" invites premature completion
on exactly the findings that matter.
