# What this is, and what it can and can't tell you

Source: **Therapeutic Goods Administration (TGA)** (Australia), public data. Scope: COVID vaccines + non-COVID vaccines + all medicines; product-classified in gn_spare.

## The limits that never go away
These are *reports*, not confirmed effects — a report means someone filed it, not that the product caused the event. Counts are a floor (most events are never reported) and there is no population denominator, so a count is not a rate. Hypothesis-generating only; correlation is not causation.

## Read these per-source notes
- **Unit:** Each row is one adverse-event report.
- **`serious` is the source regulator's own determination** — definitions differ
  between regulators, so cross-jurisdiction "serious" comparisons need caution.
- **`gn_spare` = product class**, a label so a mixed source ships whole and you
  filter: covid_vaccine (155,090), non_vaccine (64,998), vaccine_other (30,815). `covid_vaccine` is runner-typed (exact); `vaccine_other`
  is a heuristic over the product name (visible in `how_vaccines_full` — verify or
  reclassify yourself); `non_vaccine` is everything else.
- **Blank cells mean "not recorded by the source," never zero** — fields the
  source doesn't carry (e.g. lot, dose, onset, state) are left blank, not invented.


## Source-specific notes
- Death outcome is NOT captured in this TGA export: gn_outcome_died is 0 for every row, so mortality analysis is not available from this data.
- vaccine_other is a heuristic over the product name (visible in how_vaccines_full); verify or reclassify yourself.
