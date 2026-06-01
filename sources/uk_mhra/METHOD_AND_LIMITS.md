# What this is, and what it can and can't tell you

Source: **Medicines and Healthcare products Regulatory Agency (MHRA)** (United Kingdom), public data. Scope: COVID-19 vaccine reactions from MHRA Drug Analysis Profiles (rows are reactions, not patient reports).

## The limits that never go away
These are *reports*, not confirmed effects — a report means someone filed it, not that the product caused the event. Counts are a floor (most events are never reported) and there is no population denominator, so a count is not a rate. Hypothesis-generating only; correlation is not causation.

## Read these per-source notes
- **Unit:** ROWS ARE INDIVIDUAL REACTIONS, not patient reports — one report can produce several rows. Count rows as reactions; there is no patient key.
- **`serious` is the source regulator's own determination** — definitions differ
  between regulators, so cross-jurisdiction "serious" comparisons need caution.
- **`gn_spare` = product class**, a label so a mixed source ships whole and you
  filter: covid_vaccine (447,845). `covid_vaccine` is runner-typed (exact); `vaccine_other`
  is a heuristic over the product name (visible in `how_vaccines_full` — verify or
  reclassify yourself); `non_vaccine` is everything else.
- **Blank cells mean "not recorded by the source," never zero** — fields the
  source doesn't carry (e.g. lot, dose, onset, state) are left blank, not invented.


## Source-specific notes
- idap_id (in cohort_or_join_thread) identifies the vaccine-product DAP (~7), not a patient case; there is no per-patient key, so report/patient counts are not derivable.
- report_date is year-granularity only (no month/day).
