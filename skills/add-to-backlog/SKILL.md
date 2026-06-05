---
name: add-to-backlog
description: Add an item to the project backlog (BACKLOG.md). Use when the user expresses intent to track future work — "add to backlog", "save that idea", "we should do X", "remember this for later", "that would be a good feature someday".
when_to_use: add to backlog, track this, remember for later, future feature, backlog item, save idea, we should, someday, good idea
model: haiku
---

If what to add is ambiguous, ask in one sentence before proceeding.

If BACKLOG.md does not exist, invoke `bootstrap-backlog` first, then continue.

Read BACKLOG.md — skim for the type-section tables and effort/value rubric only.

Classify: type (feature / improvement / bug / cleanup / known issue / limitation), effort (S/M/L), value (H/M/L).

Derive the anchor slug from the title: lowercase, spaces → hyphens, drop all characters that are not alphanumeric or hyphens.

Add a row to the correct type table using `[Title](#anchor-slug)` in the title cell. If the section has a placeholder line ("No open …") instead of a table, replace the placeholder with the table header before adding the row. Sort H→L value; within the same tier, S→L effort.

Add a detail section under `## Open`:

```
### Title
**Type:** …
**Why** — what problem this solves or value it adds
**Notes:** implementation hints, dependencies, open questions
```

Confirm in one line what was added.
