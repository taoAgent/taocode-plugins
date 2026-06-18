---
name: verify-before-done
description: Use before claiming a task is complete, fixed, working, or passing, and before committing. Run the real command and read its output first.
slash: true
---

# Verify Before Done

Claims of success must be backed by output you actually saw — not by assumption.

## Steps

1. State the claim you are about to make ("tests pass", "the build works", "the bug is fixed").
2. Run the actual command that would prove it — the test, the build, the script, the request.
3. Read the real output. Look for failures, errors, or warnings, not just that it ran.
4. Claim success only if the output confirms it.
5. If you did not or could not run it, say so plainly: "not verified".

## Rules

- Evidence before assertions, always.
- "It should work" is not "it works." Run it.
- Show or quote the output that supports the claim.
- Never report a task complete on the strength of having written the code alone.
