---
name: stake-report
description: Produce a stake and emissions report for a Bittensor hotkey or a whole subnet.
slash: true
---

# /stake-report

Generate a concise stake + emissions report.

**Usage:** `/stake-report <netuid | hotkey-ss58>`

## Steps

1. If the argument looks like an ss58 address, report that hotkey's stake across the subnets it
   appears on. If it is a number, report that subnet's top stakeholders.
2. Use the `taostats` MCP server (see `mcp.json`); if it is not connected, ask the user to connect it or set `TAOSTATS_API_KEY`.
3. Output a short table — rank, hotkey (shortened), stake (τ), daily emission (τ), and
   validator?/miner? — then one line of interpretation.

Read-only: this never signs or submits anything.
