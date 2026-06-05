# Example: bootstrap-changelog

> **Internal skill** — not invoked directly by the user.
> Called automatically by `ship-from-backlog` when CHANGELOG.md is missing.

## When it runs

A user triggers `/ship-from-backlog` on a project that has no `CHANGELOG.md`. Claude invokes `bootstrap-changelog` first, then continues with the ship flow.

## What it creates

**CHANGELOG.md** — scaffolded with a header and Keep a Changelog / semver preamble. Empty — ready for the first release entry.

**CLAUDE.md** — appended (or created) with a `## Version tracking` section recording where the version is stored, chosen interactively:

1. `package.json` — bumps `"version"` field on each release
2. `VERSION` file — plain text file at repo root
3. CHANGELOG.md only — latest `## [X.Y.Z]` heading is the canonical version

## Notes

- Asks the user exactly one question (version tracking location) before writing.
- If option 2 is chosen and no `VERSION` file exists, creates it with `0.0.0`.
