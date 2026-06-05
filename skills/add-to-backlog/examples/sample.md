# Example: add-to-backlog

## Invocation

```
/add-to-backlog
```

Or auto-triggered by phrases like: "we should add dark mode someday", "save this idea", "add to backlog".

## Sample interaction

**User:** "We should add CSV export to the reports page."

**Claude classifies:**
- Type: feature
- Effort: M
- Value: H

**Claude adds to BACKLOG.md:**

| Title | Type | Effort | Value | Notes |
|-------|------|--------|-------|-------|
| [CSV Export for Reports](#csv-export-for-reports) | feature | M | H | |

And the detail section:
```
### CSV Export for Reports
**Type:** feature
**Why** — Users can't currently get report data out of the app for use in spreadsheets.
**Notes:** Trigger from the Reports page toolbar. Use the existing data-fetching layer.
```

**Claude confirms:** "Added 'CSV Export for Reports' as a high-value, medium-effort feature."

## Notes

- If BACKLOG.md doesn't exist, `bootstrap-backlog` is called automatically first.
- Items are sorted H→M→L value, then S→M→L effort within each tier.
