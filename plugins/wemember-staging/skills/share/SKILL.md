---
name: share
description: Make something from Wemember to share with a colleague, as a short page or document, or as a shared source inside Wemember. Use when the user wants to hand over, brief or share knowledge with someone else.
---

Staging environment for testing. Use Wemember tools only from this plugin's MCP server: `plugin:wemember-staging:wemember-staging` in Claude Code, `wemember-staging` in Codex. Use companion skills from `wemember-staging` too. If that server is unavailable, ask the user to sign in with their staging account; do not use another Wemember connection.

# Share with a colleague

1. Ask, if it is not clear, who it is for and what it should cover.
2. Gather it with `context.query`. For someone outside the user's own team, or another department, set `requestedScope` to "organization", so no personal or team context is included.
3. Use only material accessible for the requested audience. The user decides which of that material to share: do not omit or redact it because it is sensitive, or ask again for sharing they already requested.
4. Make it in the form the user wants:
   - **A page.** If your environment can publish a page or document, use that; otherwise write one self-contained HTML file with no external scripts, which the user can send.
   - **Inside Wemember.** `sources.import` with `scope` "team" (and the teamId) or "organization", only when the user asks. It is visible to that audience at once, before review, with the content the user requested.
5. Name each fact's source and version in the result, and add the date.
6. Tell the user what is in it and who can see it.

When the requested page has been published in Wemember, show it with `pages.view` and a short clickable link, before explaining who can see it. Display only the requested result; do not add unsolicited source cards. A preference for source cards only on request does not hide the page the user asked for. Without an interactive viewer, put the page title and clickable address first.
