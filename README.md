# Runway — Claude Code Skill Marketplace

Workflow management skills for Claude Code. Runway gives you a structured backlog and release process driven entirely by slash commands.

## Install

```
/plugin marketplace add squalrus/runway
```

## Skills

| Skill | Command | Description |
| --- | --- | --- |
| [add-to-backlog](skills/add-to-backlog/SKILL.md) | `/add-to-backlog` | Add a feature, bug, or idea to BACKLOG.md with automatic classification and sorting |
| [ship-from-backlog](skills/ship-from-backlog/SKILL.md) | `/ship-from-backlog` | Ship a backlog item — version branch, changelog entry, version bump, build, commit, push |

## Workflow

1. Capture work with `/add-to-backlog` — Claude classifies by type, effort, and value, then writes it into `BACKLOG.md`.
2. When ready to release, run `/ship-from-backlog` — Claude creates a version branch, writes the changelog entry, bumps the version, runs the build, commits, and pushes.

First run of each skill bootstraps the files it needs (`BACKLOG.md`, `CHANGELOG.md`, `CLAUDE.md`) automatically.
