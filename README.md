# Runway — Claude Code Skill Marketplace

Workflow management skills for Claude Code. Runway gives you a structured backlog and release process driven entirely by slash commands.

## Install

```
/plugin marketplace add squalrus/runway
/plugin install runway@runway
```

## Skills

| Skill | Command | Description |
| --- | --- | --- |
| [add-to-backlog](skills/add-to-backlog/SKILL.md) | `/add-to-backlog` | Capture a feature, bug, or idea in plain English — classified by type, effort, and value, written into `BACKLOG.md` |
| [pick-from-backlog](skills/pick-from-backlog/SKILL.md) | `/pick-from-backlog` | Surface candidates from `BACKLOG.md`, brief on scope and why, and start implementing |
| [ship-from-backlog](skills/ship-from-backlog/SKILL.md) | `/ship-from-backlog` | Ship a backlog item — version branch, changelog entry, version bump, build, commit, push |

## Workflow

1. **Capture** with `/add-to-backlog` — describe the work in plain English. Claude classifies by type, effort, and value, pulls relevant code context, and writes a structured entry into `BACKLOG.md`.
2. **Pick** with `/pick-from-backlog` — Claude surfaces candidates ranked by the backlog's own ordering, briefs you on the chosen item's scope and motivation, then starts the implementation.
3. **Ship** with `/ship-from-backlog` — Claude creates a version branch, writes the changelog entry, bumps the version, runs the build, commits, and pushes.

First run of each skill bootstraps the files it needs (`BACKLOG.md`, `CHANGELOG.md`, `CLAUDE.md`) automatically.
