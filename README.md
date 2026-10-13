<p align="center">
  <a href="https://wemember.ai">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/wemember-ai/.github/main/assets/wemember-logo-white.svg">
      <img alt="Wemember" src="https://raw.githubusercontent.com/wemember-ai/.github/main/assets/wemember-logo.svg" width="260">
    </picture>
  </a>
</p>

<h3 align="center">Your company's memory in Claude Code, Codex and Cursor</h3>

<p align="center">
  <a href="plugins/wemember/LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-green?style=flat-square"></a>
  <img alt="Version 0.3.2" src="https://img.shields.io/badge/version-0.3.2-111214?style=flat-square">
  <img alt="MCP" src="https://img.shields.io/badge/MCP-app.wemember.ai%2Fmcp-111214?style=flat-square">
</p>

---

Wemember is company memory and a toolkit for organizational AI agents, delivered as an MCP layer under the AI tools your team already uses. Your agents read sources and knowledge they are allowed to see, and propose new memory for people to review.

This repository is the plugin marketplace for **Claude Code**, **Codex** and **Cursor**. The plugin connects the Wemember MCP server (`https://app.wemember.ai/mcp`) with your own sign-in and adds skills and, in Claude Code and Codex, session hooks. You need a Wemember account.

## What you get

| | Claude Code | Codex | Cursor |
| --- | :---: | :---: | :---: |
| Wemember MCP tools (OAuth sign-in) | ✓ | ✓ | ✓ |
| Eight skills (`wemember`, `catch-up`, `remember`, `correct`, `import-docs`, `share`, `company-skills`, `setup`) | ✓ | ✓ | ✓ |
| Relevant context at the first prompt of a session | ✓ | ✓ | – |
| Memory proposals at the end of longer sessions (off by default) | ✓ | ✓ | – |

Details, including exactly what the plugin sends and stores: [plugins/wemember/README.md](plugins/wemember/README.md).

## Install

### Claude Code

```
/plugin marketplace add wemember-ai/plugin
/plugin install wemember@wemember
```

Then run `/mcp`, choose the plugin's Wemember server and sign in.

### Codex (CLI and the ChatGPT desktop app)

```
codex plugin marketplace add wemember-ai/plugin
```

Install Wemember from `/plugins`, sign in with `codex mcp login wemember`, and trust its hooks in `/hooks`.

### Cursor

- **Team marketplace:** Dashboard → Plugins & MCPs → Add Marketplace → Import from Repo `wemember-ai/plugin`. Install Wemember from Customize, then sign in when the Wemember MCP server asks for OAuth.
- **Local:** copy or symlink `plugins/wemember` to `~/.cursor/plugins/local/wemember`, run *Developer: Reload Window*, and check skills and MCP under Customize.

### Other MCP clients

Without the plugin, add `https://app.wemember.ai/mcp` as a remote (HTTP) MCP server and sign in when asked.

## Configuration

| Setting | Default | What it does |
| --- | --- | --- |
| `propose_memories` | `false` | After a session with at least 15 tool calls, the agent is asked once to propose up to three decisions, preferences or agreements you stated, as personal proposals for review. Claude Code and Codex only. |

How to turn parts on or off, automatic updates, and a ready-made setup for administrators: see [Turn it on or off](plugins/wemember/README.md#turn-it-on-or-off) and [Updates](plugins/wemember/README.md#updates).

## Repository layout

| Path | What |
| --- | --- |
| `plugins/wemember/` | The plugin: manifests for Claude Code, Codex and Cursor, the MCP connection, hooks, one script and eight skills |
| `plugins/wemember-staging/` | The same plugin pointed at the Wemember staging environment, for testing |
| `.claude-plugin/marketplace.json` | Claude Code marketplace |
| `.agents/plugins/marketplace.json` | Codex marketplace |
| `.cursor-plugin/marketplace.json` | Cursor marketplace |

## Support and security

- Questions and bugs: [open an issue](https://github.com/wemember-ai/plugin/issues).
- Security problems: report them privately via [Security → Report a vulnerability](https://github.com/wemember-ai/plugin/security/advisories/new). See the [security policy](https://github.com/wemember-ai/.github/blob/main/SECURITY.md).

## License

[MIT](plugins/wemember/LICENSE) © 2026 Wemember.

<p align="center"><a href="https://wemember.ai">wemember.ai</a></p>
