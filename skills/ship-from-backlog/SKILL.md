---
name: ship-from-backlog
description: Ship a backlog item — create a version branch, write the changelog entry, bump the version, build, commit, and push. Use when the user signals readiness to release -  "ready to commit", "ship this", "let's push", "time to release", "I'm done with X".
when_to_use: ready to commit, ship this, push it, time to release, let's release, done with, commit and push, ship it, release this, I'm done
model: haiku
metadata:
  dependencies:
    - name: GitHub CLI
      command: gh
      install: https://cli.github.com
      reason: opens pull requests via `gh pr create`
---

If what's shipping isn't clear from context, ask in one sentence before proceeding.

Before starting the automated branch/commit/push/PR sequence, ask the user whether they want to test, validate, or fix anything first, or are ready to proceed now. Wait for their answer — do not start the steps below until they confirm they're ready.

**Steps — run in order, do not skip:**

1. If CHANGELOG.md does not exist, invoke `bootstrap-changelog` first. Read CLAUDE.md for the `## Version tracking` section to determine where the version is stored. Then read the current version from the appropriate source:
   - `package.json` → `"version"` field
   - `VERSION` file → file contents
   - CHANGELOG.md only → latest `## [X.Y.Z]` heading (or `0.0.0` if no entries yet)

   Also read BACKLOG.md to find the item and its type. Stop once you have the item type and current version.

2. **Semver bump:** feature → minor (reset patch); bug / improvement / cleanup / known issue / limitation → patch; breaking change → major (reset minor + patch). Confirm with the user if ambiguous.

3. `git switch -c vX.Y.Z main`

4. **CHANGELOG.md** — insert a new block at the top (below the heading and intro):
   ```
   ## [X.Y.Z] — YYYY-MM-DD
   ### Added / Changed / Fixed / Removed
   - **Name.** User-facing summary of what changed and why. (`src/file.tsx`, …)
   ```
   Only include subsections with entries. Use today's date.

5. **BACKLOG.md** — remove the item's table row (the title cell may be a `[Title](#anchor)` link — match on the display text) and its detail section. If removing the row leaves the table empty (only the header row remains), replace the entire table with a placeholder line matching the section: "No open feature items." / "No open improvement items." / "No open known issues." / "No open limitations." Keep the section heading. Touch nothing else.

6. **Docs** — update only where reality changed: CLAUDE.md (new patterns/gotchas), CONTRIBUTING.md (schema/RLS/env/scripts), README.md (user-visible changes), FAQ/Privacy/Terms/Press (copy claims), robots.txt (new routes). Skip if none apply.

7. Bump the version in whichever location CLAUDE.md documents:
   - `package.json` → set the `"version"` field only
   - `VERSION` file → overwrite with the new version string only
   - CHANGELOG.md only → skip this step; the new entry added in step 4 is the version record

8. `npm run build` — fix any errors before continuing. Do not commit a broken build.

9. Stage all changed files. Commit: `git commit -m "vX.Y.Z — short description"`

10. `git push -u origin vX.Y.Z`. Then run `gh --version` to check whether GitHub CLI is installed. If the command fails, inform the user that opening a PR requires GitHub CLI (https://cli.github.com) and stop here. If available, run `gh pr create --base main --fill` to open the pull request.
