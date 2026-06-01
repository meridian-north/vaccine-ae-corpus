# Canada Vigilance (CVAR) — vaccines — open dataset + query kit

A clean, searchable copy of Health Canada — Canada Vigilance (CVAR) adverse-event data (Canada), in the
universal 69-column who/what/when/where/how format — the same schema as the VAERS
(US), CVAR (Canada) and UK MHRA bundles, so they can be queried side by side.

**Scope:** vaccine adverse-event reports (is_vaccine_case = true); product typing partial.
**Rows:** 29,501. Each row is one adverse-event report.
**Product classes (`gn_spare`):** vaccine_other (19,335), covid_vaccine (10,166).

**No personal information.** Built only from structured, coded fields; free-text
narrative is not included.

## Start here
1. Open `data/sample_1000.csv` — a taster (any spreadsheet, or the queries below).
2. Skim `QUERIES.md`; read `METHOD_AND_LIMITS.md` before quoting numbers.
3. Filter by `gn_spare` to pick a product class (e.g. `covid_vaccine`).
4. Full file: `data/cvar_vaccine_1965_2026_69col.csv.gz`.

## What's in the bundle
```
README.md  INDEX.md  QUERIES.md  METHOD_AND_LIMITS.md
SOURCE_AND_VERIFICATION.md  FAQ.md  MANIFEST_SHA256.txt
data/cvar_vaccine_1965_2026_69col.csv.gz            <- full dataset
data/sample_1000.csv
data/extracts/              <- pre-pulled rows + aggregates (incl by_product_class.csv)
```

*Public-domain source. PII-free derivative. The method travels with the data.*
