# Changelog

User-visible changes, newest first. Follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) format and [semver](https://semver.org/) versioning.

## [1.1.0] — 2026-06-07

### Added

- **Skill PR opening.** The ship workflow can now open pull requests via `gh pr create` after pushing the release branch, with a pre-flight check so users can test, validate, or fix things before the automated sequence runs. Requires the GitHub CLI. (`skills/ship-from-backlog/SKILL.md`, `skills/bootstrap-backlog/SKILL.md`, `BACKLOG.md`, `CLAUDE.md`)

### Changed

- **Backlog scanning on bare invocation.** When `/ship-from-backlog` runs without parameters, it now scans BACKLOG.md for items that already landed but were never removed, and ships that item. (`skills/ship-from-backlog/SKILL.md`)
