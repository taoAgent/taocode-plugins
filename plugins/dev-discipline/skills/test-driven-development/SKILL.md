---
name: test-driven-development
description: Use when implementing a new feature, function, or bug fix, before writing implementation code. Write a failing test first, then the minimal code to pass it. Triggers on "add", "implement", "build", "fix", "write a function", or any change to behavior that should be tested.
slash: true
---

# Test-Driven Development

Write the test before the code. The test defines what "done" means and proves the code works.

## Steps

1. Pick the next single behavior to add.
2. Write one small test that asserts that behavior. Keep it focused on one thing.
3. Run the test and watch it fail — confirm it fails for the expected reason (not a typo or import error).
4. Write the minimal code to make that test pass. No extra features.
5. Run the test and confirm it passes.
6. Refactor if needed, keeping all tests green.
7. Repeat for the next behavior.

## Rules

- Never write implementation code before a failing test exists for it.
- One behavior per test; a test that checks many things hides which one broke.
- See the test fail first — a test that never failed proves nothing.
- Keep steps small: red → green → refactor, then repeat.
