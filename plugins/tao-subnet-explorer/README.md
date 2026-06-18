# TAO Subnet Explorer

Read-only tooling for understanding Bittensor subnets without leaving a TaoCode session.

## What's inside

- **`subnet-metagraph`** (model-invoked) — activates when you ask about a subnet's validators, stake
  distribution, consensus, or emissions, and answers in plain terms.
- **`/stake-report`** (slash command) — a quick stake + emissions report for a hotkey or subnet.
- **`taostats` MCP server** (`mcp.json`) — the data source both skills read from.

## Configuration

Both skills read through the `taostats` MCP server, which needs an API key:

```bash
export TAOSTATS_API_KEY="…"
```

Point the endpoint in `mcp.json` at your preferred provider if you aren't using the default. With no
data source configured, the skills ask you to set the key or connect the server rather than guess
numbers.

## Safety

Everything here is **read-only**. No skill in this plugin signs, stakes, or transfers. For anything
that touches a wallet, use `tao-wallet-guard`.
