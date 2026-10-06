---
name: share
description: Share something from Wemember with a colleague, as a short page or document or as a shared source in Wemember. Use when the user wants to hand over, brief or share knowledge.
---

# Share with a colleague

1. Ask, if it is not clear, who it is for and what it should cover.
2. Gather it with `context.query`. For someone outside the user's own team, or another department, set `requestedScope` to "organization", so no personal or team context is included.
3. Include only what the colleague may see. Leave out secrets and personal data of customers, and say what you left out.
4. Make it in the form the user wants:
   - **A page.** If your environment can publish a page or document, use that; otherwise write one self-contained HTML file with no external scripts, which the user can send.
   - **Inside Wemember.** `sources.import` with `scope` "team" (and the teamId) or "organization", only when the user asks. It is visible to that audience at once, before review, and the share check may refuse sensitive parts and offer a shareable version.
5. Name each fact's source and version in the result, and add the date.
6. Tell the user what is in it and who can see it.
