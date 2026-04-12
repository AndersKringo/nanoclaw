---
name: jobindex-search
description: Search live Danish job listings from Jobindex.dk — Denmark's largest job portal with broad private sector coverage. Use for keyword-based searches across all industries and seniority levels.
allowed-tools: Bash(jobindex:*)
---

# Jobindex Search

Search Denmark's largest job portal.

## Commands

```bash
jobindex search --query "CTO Copenhagen" --format json
jobindex search --query "transformation director" --jobage 14
jobindex detail <job-id>
```

## Search options

| Flag | Description |
|------|-------------|
| `--query` / `-q` | Keyword search — include city in query for location filtering |
| `--jobage` | Max posting age in days: `1`, `7`, `14`, `30`, `9999` (all, default) |
| `--sort` | `score` (relevance, default) or `date` (newest first) |
| `--page` | Page number (20 results per page) |
| `--limit` | Cap results client-side |
| `--format` | `json` (default), `table`, `plain` |

## Notes

- No area filter via API params — include city name in `--query` instead (e.g. `"director copenhagen"`)
- Returns 20 results per page; use `--page` to paginate
- `meta.total` shows the full result count
