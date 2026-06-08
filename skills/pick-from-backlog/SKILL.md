---
name: pick-from-backlog
description: Pick an item (or items) from the backlog (BACKLOG.md) and start implementing it. Use when the user wants to start work on backlog work — "what should I work on next", "let's pick something from the backlog", "start on X", "pick a backlog item".
when_to_use: pick from backlog, what's next, what should I work on, start on, let's build, work on this, implement from backlog, next backlog item, pick something to build
---

If BACKLOG.md does not exist, tell the user there's nothing to pick from yet and stop — suggest `add-to-backlog` once they have ideas worth tracking.

Read BACKLOG.md in full: the type-section tables (for the suggested execution order — H→L value, then S→L effort within tier) and the `## Open` detail sections (for **Why** / **Notes**).

**Selecting the item:**
- If the user named a specific item, or it's clear from context which one(s) they mean, locate it by title match across the tables and detail sections.
- Otherwise, propose 2-3 candidates ranked by the backlog's own ordering. For each, give type, effort, value, and a one-line "why" so the user can choose with real information. Wait for their pick — do not assume which one to start.
- The user may pick more than one related item to implement together; treat that as a single scope once confirmed.

**Briefing before writing code:**
Summarize the chosen item's **Why** and **Notes** back to the user in a sentence or two so you're aligned on scope before starting. If Notes surfaces open questions or dependencies, resolve those with the user now rather than guessing mid-implementation.

**Starting the work:**
- Break the item into concrete implementation steps with TodoWrite if it's larger than a single change.
- Implement on the current branch. This skill does not create release branches or touch versioning — `ship-from-backlog` handles that when the work is ready to ship.
- Leave the BACKLOG.md entry in place; it's removed when the item ships, not when work starts.

State in one line which item you're starting and what the first concrete step is.
