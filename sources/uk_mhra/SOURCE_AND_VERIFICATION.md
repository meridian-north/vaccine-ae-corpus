# Source & verification

## Where this comes from
Medicines and Healthcare products Regulatory Agency (MHRA) (United Kingdom), public adverse-event data:
> https://yellowcard.mhra.gov.uk/

This dataset is a **structured, PII-free derivative** — built only from coded
fields, so it carries no personal identifiers. We point to the regulator's own
copy rather than re-host their raw (which can contain free-text identifiers).

## How to verify
1. Check any file against `MANIFEST_SHA256.txt` (`shasum -a 256 <file>`).
2. Re-derive from the source with the published method (same input + same seed →
   same output).
3. Spot-check a row: `gn_sha256` (where present) hashes the source record;
   `how_vaccines_full` carries the product name so you can confirm the
   `gn_spare` class yourself.

Prepared 2026-06-01. Public-domain source; CC0 derivative.
