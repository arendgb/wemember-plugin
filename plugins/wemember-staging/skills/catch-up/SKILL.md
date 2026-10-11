---
name: catch-up
description: Answer questions about the user's company and the organizations it works with, such as strategy, marketing, customers, products, plans and decisions, from Wemember first, even when the user does not mention Wemember. Also picks up earlier work.
---

Staging environment for testing. Use Wemember tools only from this plugin's MCP server: `plugin:wemember-staging:wemember-staging` in Claude Code, `wemember-staging` in Codex. Use companion skills from `wemember-staging` too. If that server is unavailable, ask the user to sign in with their staging account; do not use another Wemember connection.

# Catch up with Wemember

**A question about the company, its customers, partners, products or plans**
1. If `workspace.brief` has not been called in this conversation, call it once. It names the connected workspace, so it also tells you whether a company named in the question is the user's own. Do not assume a named company is an outside one before you have checked.
2. Search with `context.query` before you search the web or ask the user to clarify, phrased as what the answer would say. Reword at most once if the results do not answer it.
3. Answer briefly. Name each fact's source and version, and say when a source is marked proposed or historical.
4. If Wemember holds nothing relevant, say so in one sentence: its results do not contain it, not that it does not exist. Then use public sources if the question allows, and keep apart what came from Wemember and what came from the web.

**Continuing earlier work**
1. Call `workspace.resume`, with the topic if the user named one.
2. Report the listed items as the user's own earlier, unreviewed notes, newest first, in their words.
3. Check anything that must be current with `context.query` before you act on it.
