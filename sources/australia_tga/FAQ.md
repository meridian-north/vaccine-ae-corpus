# FAQ — TGA DAEN — Australia

**Does this prove the product caused these events?** No. These are *reports*, not confirmed effects — a report means someone filed it, not that the product caused the event. Counts are a floor (most events are never reported) and there is no population denominator, so a count is not a rate. Hypothesis-generating only; correlation is not causation.

**What's `gn_spare`?** A product-class label so the dataset ships whole and you
filter: covid_vaccine (155,090), non_vaccine (64,998), vaccine_other (30,815). Filter `gn_spare='covid_vaccine'` for the COVID-vaccine
subset; `non_vaccine` is non-vaccine medicines.

**Can I compute a rate?** Not from this file alone — there's no denominator
(doses/person-time). Counts are a floor.

**Is there personal information?** No — structured fields only; no free-text.

**Why might row-count not equal report-count?** Each row is one adverse-event report.

**Cross-jurisdiction?** This uses the same 69-column schema as the US/Canada/UK
bundles, so `gn_spare='covid_vaccine'` gives an apples-to-apples COVID comparison
across them — with the per-regulator caveats above.
