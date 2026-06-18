# TaoCode Plugins

The official plugin registry for [TaoCode](https://taocode.io) — installable **skills** and **MCP servers** for the TaoCode CLI.

Browse and install these from inside TaoCode with the `/plugins` command.

## Using this registry

In TaoCode, run `/plugins` to browse, install, and uninstall plugins. To use this registry as a custom source, point TaoCode at this repository's `registry.json`.

## What a plugin provides

Each plugin lives under `plugins/<id>/` and declares what it provides in `plugin.json`:

- **Skills** — instruction files (`skills/<name>/SKILL.md`) that extend what the agent knows how to do. On install they're materialized into a directory TaoCode scans, so they're available with no config edit.
- **MCP servers** — declared in an `mcp.json` (`{ "servers": { … } }`) and merged into your config on install.

## Repository layout

```
registry.json              # the catalog this registry publishes
plugins/
  <id>/
    plugin.json            # { "provides": { "skills": [...], "mcp": "mcp.json" } }
    skills/<name>/SKILL.md
    mcp.json               # optional — MCP server definitions
```

## Contributing a plugin

1. Create `plugins/<id>/` with a `plugin.json` plus your `skills/` and/or `mcp.json`.
2. Add an entry to the `plugins` array in `registry.json` — `id`, `label`, `summary`, `trust`, and `origin: { "type": "local", "path": "./plugins/<id>" }`.
3. Open a pull request.

Entries are marked `verified` (maintained by the TaoCode team) or `community`.

## Maintainer

taoAgent · taoAgent@taocode.io · <https://taocode.io>
