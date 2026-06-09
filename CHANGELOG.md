# Changelog

User-visible changes, newest first. Follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) format and [semver](https://semver.org/) versioning.

## [1.2.1] — 2026-06-08

### Changed

- **README skill descriptions.** Rewrote the skill table descriptions and workflow steps for clarity — each entry now surfaces what Claude does (classifies, ranks, briefs) rather than just naming the action. (`README.md`)

## [1.2.0] — 2026-06-07

### Added

- **pick-from-backlog skill.** New `/pick-from-backlog` command that reads BACKLOG.md, helps choose item(s) to start on (ranked by the backlog's own value/effort ordering when ambiguous), briefs on the chosen item's Why/Notes, and kicks off implementation with TodoWrite. Branching and versioning stay with `ship-from-backlog`. (`skills/pick-from-backlog/SKILL.md`, `.claude-plugin/marketplace.json`, `README.md`)

### Changed

- **Changelog coverage for non-backlog changes.** `/ship-from-backlog` now diffs the shipping changes against the backlog item(s) being shipped and classifies any other changes (ad hoc fixes, refactors, docs, etc.) into the changelog alongside the backlog entries, so nothing ships unrecorded. (`skills/ship-from-backlog/SKILL.md`)

## [1.1.0] — 2026-06-07

### Added

- **Skill PR opening.** The ship workflow can now open pull requests via `gh pr create` after pushing the release branch, with a pre-flight check so users can test, validate, or fix things before the automated sequence runs. Requires the GitHub CLI. (`skills/ship-from-backlog/SKILL.md`, `skills/bootstrap-backlog/SKILL.md`, `BACKLOG.md`, `CLAUDE.md`)

### Changed

- **Backlog scanning on bare invocation.** When `/ship-from-backlog` runs without parameters, it now scans BACKLOG.md for items that already landed but were never removed, and ships that item. (`skills/ship-from-backlog/SKILL.md`)
