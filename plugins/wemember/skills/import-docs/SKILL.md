---
name: import-docs
description: Put documents into Wemember as sources, so the user's and their team's AI tools can find them. Use when the user asks to add, import or sync text or Markdown files into Wemember.
---

# Import documents into Wemember

1. List the files you plan to import, with the audience, and wait for the user's go.
   - Wemember takes text and Markdown. Tell the user that PDF and Word files are not supported yet.
   - Skip secrets, `.env` and credential files, and anything with personal data of customers.
2. Audience: personal by default. Use `team` (with its teamId) or `organization` only when the user asks. A shared source is visible to that audience at once, before any review, and Wemember's share check may refuse sensitive parts.
3. Import:
   - **Files that will change later**, such as docs in a repository: `sources.upsert` with a stable `externalId` and `relativePath` (the file's path in the repository), `sourceSystem` "git", and `documentStatus` "current" unless the user says otherwise. Running it again adds a new version instead of a copy.
   - **One-off text**: `sources.import` with a clear title.
   - **Several files**: when the tool's input offers `items`, send them in batches of up to 25 per call (`{ items: [ ...one single-call input per file ] }`, with `expectedVersion` per item when updating). Each item is checked on its own; read every item's `ok` in the answer, retry `rate_limited` items after a minute, and report the others' errors. Without `items` in the schema, call once per file.
4. Report what was imported, to whom it is visible, and what was skipped and why.
