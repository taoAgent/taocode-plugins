# Chutes Gateway Kit

Understand and triage TAO inference gateway funding from inside TaoCode.

## What's inside

- **`gateway-balance`** (model-invoked) — activates on questions about Chutes/Targon balance or
  `402 payment required`, and explains funding state and how to top up.

## How it reads state

It uses the same sources TaoCode does — `auth.json`, the `TAOCODE_API_KEY` / `CHUTES_API_KEY` /
`TARGON_API_KEY` env vars, and the wallet config at `~/.chutes/config.ini` (including its
`[payment] address` TAO deposit address).

## Safety

Read-only. This plugin never signs, stakes, transfers, or mints — it only explains the funding
picture. Key values are never printed back.
