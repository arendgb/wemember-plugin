---
name: correct
description: Fix or take back something stored in Wemember. Use when the user says a remembered statement or a piece of company knowledge is wrong, outdated, or should be forgotten.
---

# Correct Wemember

1. Find the item: `workspace.resume` for the user's own recent notes, otherwise `memory.list` or `context.query`. Note its memoryId and version.
2. Then, depending on the item:

   | Item | User wants | Tool |
   | --- | --- | --- |
   | the user's own note, not yet published | a correction | `memory.revise` with the exact correction. For a partial correction, read `memory.history` and pass `currentStatement` with the unchanged details. |
   | the user's own note, not yet published | to take it back | `memory.withdraw` |
   | published knowledge, or someone else's note | a correction | `memory.feedback` with a readable correction. It goes to the review queue; a reviewer changes or revokes it in the Wemember web app. |

3. Never save a correction or a retraction as a new statement.
4. Confirm in one sentence what changed, or that it awaits a reviewer.
