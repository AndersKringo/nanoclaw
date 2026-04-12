---
name: jobdanmark-search
description: Search live Danish job listings from Jobdanmark.dk — 15,000+ active listings with strong private sector coverage. Use for keyword and category-based searches with municipality and job-type filtering.
allowed-tools: Bash(jobdanmark:*)
---

# Jobdanmark Search

Search Jobdanmark.dk — broad private sector coverage.

## Commands

```bash
jobdanmark search --text "transformation" --format json
jobdanmark search --text "CIO" --municipality "København"
jobdanmark search --text "director" --job-type fuldtid
jobdanmark detail <job-slug>
jobdanmark categories                     # list category IDs
jobdanmark autocomplete --query "leder"   # suggest job titles
jobdanmark locations --query "aarhus"     # suggest locations
```

## Search options

| Flag | Description |
|------|-------------|
| `--text` | Free-text keyword search |
| `--category` | Category ID (use `categories` command to list) |
| `--jobtitle-id` | Job title ID from `autocomplete` results |
| `--municipality` | Municipality name (e.g. `København`, `Aarhus`) |
| `--zip` | Zip code |
| `--region` | Region name |
| `--job-type` | Comma-separated: `fuldtid`, `deltid`, `fleksjob`, `elev`, `studiejob`, `praktik` |
| `--page` | Page number (30 results per page, server-enforced) |
| `--limit` | Cap results client-side |
| `--format` | `json` (default), `table`, `plain` |

## Notes

- Pages are fixed at 30 items server-side
- `meta.totalItems` shows the full result count
- Use `jobdanmark categories` to browse the category taxonomy
