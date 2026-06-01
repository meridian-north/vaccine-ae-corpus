# UK MHRA Yellow Card — COVID vaccines — open dataset + query kit

A clean, searchable copy of Medicines and Healthcare products Regulatory Agency (MHRA) adverse-event data (United Kingdom), in the
universal 69-column who/what/when/where/how format — the same schema as the VAERS
(US), CVAR (Canada) and UK MHRA bundles, so they can be queried side by side.

**Scope:** COVID-19 vaccine reactions from MHRA Drug Analysis Profiles (rows are reactions, not patient reports).
**Rows:** 447,845. ROWS ARE INDIVIDUAL REACTIONS, not patient reports — one report can produce several rows. Count rows as reactions; there is no patient key.
**Product classes (`gn_spare`):** covid_vaccine (447,845).

**No personal information.** Built only from structured, coded fields; free-text
narrative is not included.

## Start here
1. Open `data/sample_1000.csv` — a taster (any spreadsheet, or the queries below).
2. Skim `QUERIES.md`; read `METHOD_AND_LIMITS.md` before quoting numbers.
3. Filter by `gn_spare` to pick a product class (e.g. `covid_vaccine`).
4. Full file: `data/uk_mhra_vaccine_69col.csv.gz`.

## What's in the bundle
```
README.md  INDEX.md  QUERIES.md  METHOD_AND_LIMITS.md
SOURCE_AND_VERIFICATION.md  FAQ.md  MANIFEST_SHA256.txt
data/uk_mhra_vaccine_69col.csv.gz            <- full dataset
data/sample_1000.csv
data/extracts/              <- pre-pulled rows + aggregates (incl by_product_class.csv)
```

*Public-domain source. PII-free derivative. The method travels with the data.*
