---
name: bootstrap-changelog
description: One-time scaffolding of CHANGELOG.md for projects that don't have one. Called by ship-from-backlog when CHANGELOG.md is missing — not triggered directly from conversation.
user-invocable: false
model: haiku
---

Create CHANGELOG.md with this content:

```markdown
# Changelog

User-visible changes, newest first. Follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) format and [semver](https://semver.org/) versioning.
```

Then ask the user — in a single message, one question:

> Where should the current version be tracked?
> 1. `package.json` — bump the `"version"` field on each release
> 2. `VERSION` file — a plain text file at the repo root containing only the version string
> 3. CHANGELOG.md only — derive the current version from the latest `## [X.Y.Z]` heading; no separate file is maintained

Wait for the answer, then append a `## Version tracking` section to CLAUDE.md (create CLAUDE.md if it doesn't exist):

- Option 1: `Version is tracked in \`package.json\` (the \`"version"\` field).`
- Option 2: `Version is tracked in \`VERSION\` (plain text file at the repo root).`
- Option 3: `Version is derived from CHANGELOG.md — the latest \`## [X.Y.Z]\` heading is the current version. No separate version file is maintained.`

If the user picks option 2 and no `VERSION` file exists, create one containing `0.0.0`.

Report what was created and the version tracking decision, then return to the caller.
