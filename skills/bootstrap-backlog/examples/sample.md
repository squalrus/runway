# Example: bootstrap-backlog

> **Internal skill** — not invoked directly by the user.
> Called automatically by `add-to-backlog` when BACKLOG.md is missing.

## When it runs

A user triggers `/add-to-backlog` on a project that has no `BACKLOG.md`. Claude invokes `bootstrap-backlog` first, then continues with the add-to-backlog flow.

## What it creates

**BACKLOG.md** — scaffolded with:
- Shipping instructions (branch, changelog, semver bump, build, commit, push)
- Effort/value rubric (S/M/L, H/M/L)
- Empty section tables for: Features, Improvements, Known issues, Limitations
- An `## Open` detail section

**CLAUDE.md** — either created or appended with a `## Working with the backlog` section linking to BACKLOG.md and summarizing the shipping workflow.

## Notes

- Safe to call multiple times — it checks for existing files before writing.
- Does not create duplicate CLAUDE.md backlog sections if one already exists.
