# TAO Wallet Guard

Guardrails that make Bittensor wallet actions deliberate from inside TaoCode.

## What's inside

- **`transfer-preview`** (model-invoked) — activates before any TAO transfer,
  stake/unstake, or delegation; restates the action in plain terms, flags risk,
  and requires explicit confirmation before anything is signed.

## Safety

This plugin never holds keys, signs, or broadcasts — it is a confirmation gate
that explains what is about to happen and pauses for a yes. Pair it with
`tao-subnet-explorer` (read-only chain inspection) and `chutes-gateway-kit`
(inference funding) for a read-only-plus-guarded-write toolkit.
