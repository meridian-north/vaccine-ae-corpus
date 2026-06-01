# Query pack — UK MHRA Yellow Card — COVID vaccines

Load (DuckDB reads .gz directly): `CREATE VIEW v AS SELECT * FROM read_csv_auto('data/uk_mhra_vaccine_69col.csv.gz', header=true, all_varchar=true);`
Read `METHOD_AND_LIMITS.md` first. `gn_spare` is the product class.

```sql
-- product-class split (ship-whole, filter-yourself)
SELECT gn_spare, count(*) FROM v GROUP BY 1 ORDER BY 2 DESC;

-- COVID-vaccine subset, reports by year
SELECT gn_report_date[1:4] AS year, count(*) FROM v
WHERE gn_spare='covid_vaccine' GROUP BY 1 ORDER BY 1;

-- deaths by product (manufacturer/medicine name)
SELECT gn_mfr_name, count(*) AS reports,
       count(*) FILTER (WHERE gn_outcome_died='1') AS deaths
FROM v GROUP BY 1 ORDER BY deaths DESC;

-- myocarditis/pericarditis, males under 30 (controlled cut)
SELECT gn_report_date[1:4] AS year, count(*) FROM v
WHERE (what_symptoms_full ILIKE '%myocard%' OR what_symptoms_full ILIKE '%pericard%')
  AND gn_sex='M' AND TRY_CAST(gn_age_years AS DOUBLE) < 30
GROUP BY 1 ORDER BY 1;

-- pregnancy-related
SELECT * FROM v WHERE what_symptoms_full ILIKE '%pregnan%'
   OR what_symptoms_full ILIKE '%miscarriage%' OR what_symptoms_full ILIKE '%fetal%';
```
The `extracts/` folder has these already pulled. Run `SELECT *` for the rows.
