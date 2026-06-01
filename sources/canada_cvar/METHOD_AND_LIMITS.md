# What this is, and what it can and can't tell you

Source: **Health Canada — Canada Vigilance (CVAR)** (Canada), public data. Scope: vaccine adverse-event reports (is_vaccine_case = true); product typing partial.

## The limits that never go away
These are *reports*, not confirmed effects — a report means someone filed it, not that the product caused the event. Counts are a floor (most events are never reported) and there is no population denominator, so a count is not a rate. Hypothesis-generating only; correlation is not causation.

## Read these per-source notes
- **Unit:** Each row is one adverse-event report.
- **`serious` is the source regulator's own determination** — definitions differ
  between regulators, so cross-jurisdiction "serious" comparisons need caution.
- **`gn_spare` = product class**, a label so a mixed source ships whole and you
  filter: vaccine_other (19,335), covid_vaccine (10,166). `covid_vaccine` is runner-typed (exact); `vaccine_other`
  is a heuristic over the product name (visible in `how_vaccines_full` — verify or
  reclassify yourself); `non_vaccine` is everything else.
- **Blank cells mean "not recorded by the source," never zero** — fields the
  source doesn't carry (e.g. lot, dose, onset, state) are left blank, not invented.


## Source-specific notes
- Product typing is PARTIAL: 10,166 cases are COVID-typed (gn_spare=covid_vaccine); 19,335 carry no product type (vaccine_other) and may include untyped COVID cases. So a covid_vaccine filter on CVAR is a floor, not a complete COVID count.
