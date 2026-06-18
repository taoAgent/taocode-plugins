# TaoCode Plugins

![registry](https://img.shields.io/badge/TaoCode-registry-2ea043) ![install](https://img.shields.io/badge/install-%2Fplugins-2ea043) ![provides](https://img.shields.io/badge/skills%20%2B%20MCP%20servers-grey)

The **official plugin registry** for [TaoCode](https://taocode.io) — a curated catalog of **skills** and **MCP servers** you can install straight from the CLI.

Open TaoCode and run **`/plugins`** to browse, install, and uninstall everything below — no config editing, no manual file copying.

```
/plugins        # browse the registry, then install with one keystroke
```

## Available plugins

| Plugin | Provides | Category | Trust | Summary |
| --- | --- | --- | --- | --- |
| **TAO Subnet Explorer** | Skills + MCP | bittensor | ✅ verified | Inspect Bittensor subnets — metagraph, validators, stake weights, consensus, emission split. Read-only. |
| **Chutes Gateway Kit** | Skill | inference | ✅ verified | Inspect Chutes (SN64) / Targon (SN4) gateway balance, triage 402 "payment required", explain hotkey funding. |
| **TAO Wallet Guard** | Skill | wallet | ✅ verified | Preview transfers and staking, then require explicit confirmation before any signature. |
| **Conventional Commits** | Skill | git | ✅ verified | Write clear, consistent commit messages following the Conventional Commits spec. |

**Trust levels:** `✅ verified` = built and maintained by the TaoCode team · `community` = contributed by the community (review before installing).

## How plugins work

Each plugin declares what it provides in a `.taocode-plugin/plugin.json`. There are two kinds of capability, and TaoCode wires both in for you on install:

- **Skills** — instruction files (`skills/<name>/SKILL.md`) that teach the agent how to do something (a workflow, a convention, a format). On install they're materialized into a directory TaoCode scans automatically, so the new ability is available immediately with **no config edit**. The agent loads a skill on its own when the task matches the skill's description.
- **MCP servers** — external tools and data sources, declared in an `mcp.json` (`{ "servers": { … } }`). On install the server definition is **merged into your TaoCode config**, exposing its tools to the agent.

A single plugin can ship skills, MCP servers, or both.

## Using this registry

`/plugins` clones this repository and reads its `.taocode-plugin/registry.json` by default. To use a different or self-hosted registry, add it as a **custom source** in `/plugins` — a GitHub repo (`owner/repo`) or any git URL works.

## Repository layout

```
.taocode-plugin/
  registry.json              # the catalog this registry publishes
plugins/
  <id>/
    .taocode-plugin/
      plugin.json            # { "provides": { "skills": [...], "mcp": "mcp.json" } }
    skills/<name>/
      SKILL.md               # one directory per skill
      scripts/               # optional — helpers, installed alongside the skill
    mcp.json                 # optional — { "servers": { … } }
```

## Contributing a plugin

1. Create `plugins/<id>/` with a `.taocode-plugin/plugin.json` plus your `skills/` and/or an `mcp.json`:
   ```json
   { "provides": { "skills": ["skills/<name>"], "mcp": "mcp.json" } }
   ```
2. Add an entry to the `plugins` array in `.taocode-plugin/registry.json`:
   ```json
   {
     "id": "<id>",
     "label": "<Display Name>",
     "summary": "<one-line description>",
     "category": "<git | bittensor | …>",
     "tags": ["…"],
     "trust": "community",
     "origin": { "type": "local", "path": "./plugins/<id>" }
   }
   ```
3. Open a pull request. New community entries are reviewed before they're marked `verified`.

## Maintainer

taoAgent · [taoAgent@taocode.io](mailto:taoAgent@taocode.io) · <https://taocode.io>
