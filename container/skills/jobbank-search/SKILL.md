---
name: jobbank-search
description: Search live Danish job listings from Akademikernes Jobbank (jobbank.dk) — specialised in positions for highly educated and academic candidates. Use for executive, management, IT, and specialist roles in Denmark.
allowed-tools: Bash(jobbank:*)
---

# Akademikernes Jobbank Search

Search Denmark's primary job portal for highly educated candidates.

## Commands

```bash
jobbank search --key "transformation" --format json
jobbank search --key "CIO" --location 1       # 1 = Copenhagen region
jobbank search --key "digital" --type 3       # type 3 = management
jobbank detail <job-id>
```

## Search options

| Flag | Description |
|------|-------------|
| `--key` | Keyword (title, company, skill) |
| `--exclude` | Exclude keywords |
| `--type` | Job type code (3 = management, 6 = IT) |
| `--location` | Region code (1 = Copenhagen, 2 = Aarhus) |
| `--work-area` | Function/work area code |
| `--industry` | Industry sector code |
| `--suitable-for` | Target group code |
| `--remote` | `helt` (fully remote) or `delvist` (hybrid) |
| `--since` | Posted on or after date (YYYY-MM-DD) |
| `--limit` | Cap results client-side |
| `--format` | `json` (default), `table`, `plain` |

## Workflow

1. Search to get job IDs
2. Use `detail <id>` to get full description, deadline, and application link

Results are capped at 100 by the RSS feed. `meta.total` shows the actual count.
