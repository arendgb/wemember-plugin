# Wemember for Cursor

Wemember is company memory infrastructure: one memory under the AI tools your company already uses (Claude, ChatGPT, Cursor, Grok). Your tools keep it current, within your rules, and all read from it. It is not an agent workplace.

## What you get in Cursor

- **MCP server** `wemember` at `https://app.wemember.ai/mcp` (HTTP, OAuth sign-in). No API keys in the plugin.
- **Skills**: `wemember`, `setup`, `catch-up`, `remember`, `correct`, `share`, `import-docs`, `company-skills`. Invoke with `/skill-name` or let the agent pick them.
- **No hooks in Cursor.** Session-context and memory-proposal hooks are Claude Code and Codex only. In Cursor the agent calls Wemember tools when a skill or your prompt asks for it.

## Setup

1. Install Wemember from the Cursor Marketplace (or Customize → Plugins).
2. When Cursor prompts, sign in to Wemember (OAuth) and pick the workspace(s) the agent may use.
3. Ask: "Catch me up on <project> from Wemember."

You need a Wemember account. Data handling, what is sent and how to turn it off: see [README.md](README.md).
