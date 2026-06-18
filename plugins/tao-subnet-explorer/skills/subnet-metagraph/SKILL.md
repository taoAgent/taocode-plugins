---
name: subnet-metagraph
description: >-
  Use when the user asks about a Bittensor subnet's on-chain state — its
  metagraph, validators, miners, stake weights, trust, consensus, incentive, or
  emission split. Triggers on phrasing like "subnet 64", "SN4 validators", "who
  has the most stake on netuid 19", "metagraph for the Chutes subnet", or
  "emissions breakdown". Read-only — it inspects chain state and never signs or
  submits a transaction. Do NOT use for wallet transfers or staking (see
  tao-wallet-guard) or for gateway / API-key management (see chutes-gateway-kit).
---

# Subnet metagraph lookup

Inspect a Bittensor subnet's live state and explain it in plain terms.

## When this applies

The user wants to understand a subnet (a "netuid") — who validates it, how stake and emissions are
distributed, or how a particular hotkey ranks within it.

## How to proceed

1. Resolve the **netuid** from the request (e.g. "the Chutes subnet" → 64, "Targon" → 4). If it is
   genuinely ambiguous, ask which netuid rather than guessing.
2. Pull a snapshot via the `taostats` MCP server (see `mcp.json`) — call its metagraph tool. If it is
   not connected, tell the user to connect it or set `TAOSTATS_API_KEY` (see Guardrails); never invent numbers.
3. Summarize: validator count, the top stake holders, and the emission split. Lead with the answer to
   what was actually asked — don't dump the full table unless the user wants it.

## Guardrails

- Read-only. Never use this skill to move TAO or change stake.
- Stake and emission figures are point-in-time; say so when it matters.
- If no data source is configured, tell the user to set `TAOSTATS_API_KEY` or connect the `taostats`
  MCP server — never invent numbers.
