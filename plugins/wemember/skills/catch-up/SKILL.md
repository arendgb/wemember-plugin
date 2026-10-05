---
name: catch-up
description: Find what Wemember knows about a topic, or pick up earlier work. Use when the user asks what the company knows, decided or agreed about something, or wants to continue where they left off.
---

# Catch up with Wemember

**A question about a topic**
1. Search once with `context.query`, phrased as what the answer would say. Reword at most once if the results do not answer it.
2. Answer briefly. Name each fact's source and version, and say when a source is marked proposed or historical.
3. If nothing relevant comes back, say that Wemember's results do not contain it, not that it does not exist, and name who could confirm it.

**Continuing earlier work**
1. Call `workspace.resume`, with the topic if the user named one.
2. Report the listed items as the user's own earlier, unreviewed notes, newest first, in their words.
3. Check anything that must be current with `context.query` before you act on it.
