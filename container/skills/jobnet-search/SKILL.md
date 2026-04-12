---
name: jobnet-search
description: Search live Danish job listings from Jobnet.dk — Denmark's official government job portal (STAR) with 21,000+ active listings. Use for public sector roles or broad Danish market coverage.
allowed-tools: Bash(jobnet:*)
---

# Jobnet Search

Search Denmark's official government job portal.

## Commands

```bash
jobnet search --search-string "digital transformation" --format json
jobnet search --search-string "CIO" --region HovedstadenOgBornholm
jobnet search --search-string "director" --work-hours FullTime --per-page 20
jobnet detail <job-ad-id>
jobnet occupations                    # list occupation area codes
jobnet suggestions --query "leder"    # autocomplete job titles
```

## Search options

| Flag | Description |
|------|-------------|
| `--search-string` | Free-text keyword search |
| `--region` | Region name (e.g. `HovedstadenOgBornholm`, `Midtjylland`) |
| `--work-hours` | `FullTime` or `PartTime` |
| `--duration` | `Permanent` or `Temporary` |
| `--occupation-area` | Occupation area ID (use `occupations` command to list) |
| `--postal-code` | Postal code for radius search |
| `--radius` | Radius in km (default 50) |
| `--order` | `PublicationDate` (default), `BestMatch`, `ApplicationDate` |
| `--page` | Page number |
| `--per-page` | Results per page (default 10) |
| `--limit` | Cap results client-side |
| `--format` | `json` (default), `table`, `plain` |

## Notes

- `meta.totalJobAdCount` shows the full result count
- Use `jobnet occupations` to discover valid occupation area identifiers
- Valid region names: `HovedstadenOgBornholm`, `Syddanmark`, `Midtjylland`, `Nordjylland`, `OevrigeSjaelland`
