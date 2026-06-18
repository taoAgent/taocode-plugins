---
name: refactoring
description: Use when improving the structure of existing code without changing its behavior — extracting, renaming, splitting, or simplifying. Triggers on refactor, clean up, restructure, extract, rename, simplify, tidy.
slash: true
---

# Refactoring

Improve structure while keeping behavior exactly the same, in small safe steps.

## Steps

1. Start from a green, working state — tests pass or the code runs as expected.
2. Make ONE small structural change at a time (extract a function, rename, split a file, simplify a branch).
3. Keep behavior identical — do not mix in features or bug fixes.
4. Re-run the tests or build after each change to confirm nothing broke.
5. Commit in small steps so each change is easy to review and revert.

## Rules

- Refactors and behavior changes are separate commits — never both in one.
- If there are no tests covering the code, add a characterization test first so you can prove behavior did not change.
- If a change turns out to alter behavior, stop and treat it as a feature change, not a refactor.
