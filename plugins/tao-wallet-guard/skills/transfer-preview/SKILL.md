---
name: transfer-preview
description: >-
  Use before any Bittensor wallet action that moves value — a TAO transfer, a
  stake or unstake, or a delegation change. Triggers on "send TAO", "stake to",
  "unstake from", "transfer to <ss58>", or "delegate". It previews the action in
  plain terms — source, destination, amount in τ, resulting balance — and stops
  to require explicit confirmation before anything is signed. It never holds
  keys, signs, or broadcasts a transaction itself.
---

# Wallet action preview & confirmation

Make wallet actions deliberate, never accidental.

## When this applies

The user is about to move TAO — a transfer, stake, unstake, or delegation.

## How to proceed

1. Restate the action precisely: the source coldkey/hotkey, the destination
   (ss58 or delegate), the amount in τ, and the balance that would remain.
2. Surface anything risky: an unfamiliar destination, an amount over a configured
   cap, or a balance that would fall below a safety floor.
3. **Stop and ask for explicit confirmation.** Do not proceed to any signing or
   broadcast step until the user confirms in this turn.

## Guardrails

- Never sign, broadcast, or reveal a seed / private key.
- If an amount or address is ambiguous, ask — never guess a destination.
- Treat every transfer as irreversible, and say so when confirming.
