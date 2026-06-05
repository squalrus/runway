# Example: ship-from-backlog

## Invocation

```
/ship-from-backlog
```

Or auto-triggered by: "ship this", "let's push", "ready to commit", "I'm done with X".

## Sample interaction

**User:** "Ship the CSV Export for Reports item."

**Claude reads:** BACKLOG.md (finds item, type = feature → minor bump), current version from package.json (`0.3.1` → `0.4.0`).

**Claude executes in order:**

1. `git switch -c v0.4.0 main`
2. Inserts into CHANGELOG.md:
   ```
   ## [0.4.0] — 2026-06-04
   ### Added
   - **CSV Export for Reports.** Users can now download report data as a .csv file from the Reports page toolbar.
   ```
3. Removes the item's row and detail section from BACKLOG.md.
4. Updates any docs where reality changed (README, etc.).
5. Bumps `"version"` in package.json to `"0.4.0"`.
6. Runs `npm run build` — fixes errors if any.
7. `git commit -m "v0.4.0 — CSV export for reports"`
8. `git push -u origin v0.4.0` — stops here, no PR.

## Notes

- If CHANGELOG.md is missing, `bootstrap-changelog` is called first.
- Semver rule: feature → minor; bug/improvement/cleanup → patch; breaking → major.
- The skill stops after push. Opening a PR is a separate manual step.
