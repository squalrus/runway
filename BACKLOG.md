# Backlog

Tracks future features, improvements, and known bugs. Items here are not committed work — they're candidates.

## Shipping a backlog item

1. Branch off `main` named for the target version (`vX.Y.Z`). Never commit directly to `main`.
2. Move the entry to CHANGELOG.md with a version block (date, classification, user-facing summary). Remove it from here.
3. Update docs where reality changed (README, CONTRIBUTING, etc.).
4. Pick the version by semver: feature → minor; bug / improvement / cleanup → patch; breaking → major.
5. Bump `version` in marketplace.json.
6. Run the build as the correctness gate.
7. Commit and push the branch, then open a PR with `gh pr create`. **Requires [GitHub CLI](https://cli.github.com) (`gh`) to be installed and authenticated.**

## Suggested execution order

- **Effort**: S = single turn, M = full session, L = multi-session
- **Value**: H = high user impact, M = moderate, L = polish / upkeep

### Features

| Title                                   | Effort | Value |
| --------------------------------------- | ------ | ----- |
| [Add skill PR opening](#add-skill-pr-opening) | M      | H     |

### Improvements

No open improvement items.

### Known issues

No open known issues.

### Limitations

No open limitations.

---

## Open

### Add skill PR opening

**Type:** Feature

**Why** — Skills need the ability to open pull requests programmatically, enabling automated workflows and improved user experience.

**Notes:** Investigate dependencies on GitHub API integration, authentication mechanisms, and PR template handling. Clarify what data/context the skill needs from the user before opening a PR.
