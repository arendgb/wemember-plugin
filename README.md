# Wemember plugin for Claude Code and Codex

Wemember is your company's memory: your AI tools keep it current, within your rules, and all read from it. This repository is the plugin marketplace for Claude Code and Codex. The plugin sits next to the ordinary Wemember MCP connection; you need a Wemember account.

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

## Contents

| Path | What |
| --- | --- |
| `plugins/wemember/` | the plugin: manifests for both hosts, the MCP connection, hooks, one script, one skill |
| `.claude-plugin/marketplace.json` | the Claude Code marketplace |
| `.agents/plugins/marketplace.json` | the Codex marketplace |

Questions and security reports: [issues](https://github.com/arendgb/wemember-plugin/issues). Licence: see [plugins/wemember/LICENSE](plugins/wemember/LICENSE).
