# Wemember plugin for Claude Code, Codex, and Cursor

Wemember is your company's memory: your AI tools keep it current, within your rules, and all read from it. This repository is the plugin marketplace for Claude Code, Codex, and Cursor (including Grok Bot). The plugin sits next to the ordinary Wemember MCP connection; you need a Wemember account.

What the plugin does, what it sends and stores, and how to turn it off: [plugins/wemember/README.md](plugins/wemember/README.md).

## Install

**Claude Code**

```
/plugin marketplace add arendgb/wemember-plugin
/plugin install wemember@wemember
```

Then run `/mcp`, choose the Wemember server of the plugin and sign in.

**Codex** (CLI and the ChatGPT desktop app)

```
codex plugin marketplace add arendgb/wemember-plugin
```

Install Wemember from `/plugins`, sign in with `codex mcp login wemember`, and trust its hooks in `/hooks`.

**Cursor / Grok Bot**

- **Team marketplace:** Dashboard → Plugins & MCPs → Add Marketplace → Import from Repo `arendgb/wemember-plugin`. Install Wemember from Customize, then sign in when the Wemember MCP server prompts for OAuth.
- **Local test:** copy or symlink `plugins/wemember` to `~/.cursor/plugins/local/wemember`, then Developer: Reload Window and confirm skills and MCP under Customize.
- **Public marketplace:** submit this repository at [cursor.com/marketplace/publish](https://cursor.com/marketplace/publish) for an official listing (manual review).

Session-context and memory-proposal hooks are Claude Code and Codex only; in Cursor you get the MCP tools and skills.

**Updates.** Claude Code does not update this marketplace automatically unless you turn it on. Automatic updates, and a ready-made setup for administrators in Claude Code and in Codex or ChatGPT workspaces: see [Updates](plugins/wemember/README.md#updates).

## Contents

| Path | What |
| --- | --- |
| `plugins/wemember/` | the plugin: manifests for Claude, Codex and Cursor, the MCP connection, hooks (Claude/Codex), one script and eight skills |
| `.claude-plugin/marketplace.json` | the Claude Code marketplace |
| `.agents/plugins/marketplace.json` | the Codex marketplace |
| `.cursor-plugin/marketplace.json` | the Cursor / Grok Bot marketplace |

Questions and security reports: [issues](https://github.com/arendgb/wemember-plugin/issues). Licence: see [plugins/wemember/LICENSE](plugins/wemember/LICENSE).
