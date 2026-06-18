---
name: gateway-balance
description: >-
  Use when the user asks about their TAO inference gateway account — Chutes
  (SN64) or Targon (SN4) balance, why requests return HTTP 402 / "payment
  required", or how much credit is left. Triggers on "chutes balance", "why am I
  getting 402", "top up Targon", "how much TAO is in my inference account". Reads
  local gateway config only; it never moves funds.
---

# Gateway balance & 402 triage

Help the user understand the funding state of their TAO inference gateway.

## Steps

1. Identify the gateway — Chutes (SN64) or Targon (SN4). TaoCode resolves keys from `auth.json` or the
   `TAOCODE_API_KEY` / `CHUTES_API_KEY` / `TARGON_API_KEY` environment variables; the wallet path
   reads `~/.chutes/config.ini`.
2. For a **402**, explain it means the gateway account balance is empty. Point the user at the
   account's TAO deposit address — Chutes exposes a `[payment] address` in `~/.chutes/config.ini` —
   for top-up.
3. If the gateway's billing endpoint is reachable, summarize the remaining credit.

## Guardrails

- Read-only. This skill explains funding; it never signs or submits a transaction.
- Never echo a full API key. Refer to keys by gateway and source, not value.
