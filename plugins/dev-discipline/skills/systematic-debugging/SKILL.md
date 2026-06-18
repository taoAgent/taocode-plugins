---
name: systematic-debugging
description: Use when a test fails, a bug is reported, an error or stack trace appears, or behavior is unexpected. Find the root cause before changing any code.
---

# Systematic Debugging

Understand the failure before you touch the code. Guessing wastes time and adds new bugs.

## Steps

1. Reproduce the failure reliably with the smallest possible input or command.
2. Isolate it — narrow to the smallest case that still fails, removing unrelated code or data.
3. Form ONE hypothesis about the cause. State it in a sentence.
4. Test the hypothesis — add a log line, assertion, or print, then run again.
5. Confirm the actual root cause from real output. If the hypothesis was wrong, form the next one.
6. Fix the cause, not the symptom.
7. Re-run to confirm the fix, then check that nothing else broke.

## Rules

- Never apply a fix you cannot explain.
- No random changes hoping something works — each change must test a hypothesis.
- Read the actual error and output; don't assume what it says.
- A patch that hides the symptom but leaves the cause is not a fix.
