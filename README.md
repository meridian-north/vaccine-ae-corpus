# vaccine-ae-corpus

**A transparent, reproducible, multi-country vaccine adverse-event corpus.**
Public regulatory adverse-event data, harmonized into one shared schema, with a cryptographic hash on every file so anyone can verify it against the source.

> **Read this first:** These are **counts of reports, not rates.** There is **no denominator** here, so nothing in this corpus is a risk estimate. A report is a **temporal association** between an event and a vaccination — **correlation is not causation.** This corpus surfaces patterns; it draws no conclusions. *Leads, not verdicts.*

---

## What this is

Independent regulatory adverse-event reporting systems publish their data in different formats, vocabularies, and languages, so the integrated picture is hard to assemble. This corpus takes those public extracts and projects each one into a single shared schema, so one query can reach all of them at once.

Every record traces back to its source by content hash. The build is designed to be **proof-of-path**: the data, the method, and a verifying hash travel together, so any number can be re-derived from the original government extract and checked byte-for-byte.

**Source systems in this release** *(confirm against `sources/` before publishing):*

- Canada — Canada Vigilance (CVAR)
- United Kingdom — MHRA Yellow Card
- Australia — TGA Database of Adverse Event Notifications (DAEN)
- *[add/remove to match exactly what ships in `sources/` — do not list a system that isn't in the release]*

Each system's jurisdiction-specific fields are preserved under the record's `source` block; the common fields are normalized to one schema for cross-system queries.

---

## What this is NOT

- **Not a rate, and not a risk.** No source here carries a doses-administered denominator. Counts are a **floor** — most events are never reported at all. A larger count is not a more dangerous vaccine.
- **Not causation.** An event reported after a vaccination is a reported temporal association, unverified, and nothing here establishes that a vaccine caused an event.
- **Not a position on vaccine safety.** This corpus takes **no position** on whether any vaccine is safe or unsafe, at the population or individual level. Conclusions belong to the party drawing them, not to this project.
- **Not a clinical, regulatory, or medical document.** Nothing here is medical advice, a regulatory filing, or a clinical claim.
- **Not adjudicated.** Suspect or anomalous records are **flagged and kept** — never silently corrected, never silently dropped. Empty cells are **left empty** — never filled with a guess.

The caveats are not a footnote. They are meant to travel **with the data** — in the manifest, in the table headers, in the row — wherever a number goes.

---

## How to verify it yourself

This corpus is built to be checked, not trusted.

1. **Per-file integrity.** Every file is listed in `MANIFEST_SHA256.txt` *(confirm filename)* with its SHA-256. Re-hash any file and compare — change one byte and the hash changes.
2. **Trace to source.** Each record carries a content hash back to the original public extract. Download the source from the issuing agency and confirm the decomposition is faithful.
3. **Re-run the queries.** The query tooling is public *(see `sources/` / scripts)*; same input, same result, every time.

```
# example: verify a file against the manifest
sha256sum -c MANIFEST_SHA256.txt
```

**What you can verify today vs. what you cannot yet:** per-file hashes and source-tracing are verifiable from this release alone. Any chain-anchor / external-timestamp fields should be treated as **opaque provenance tokens awaiting external attestation** until the verification surface is public. This is stated as an honesty marker, not a defect — missing attestation is surfaced, never faked. *[Confirm this paragraph matches this repo's actual anchor status; remove if not applicable.]*

---

## Privacy

This is an **L0 / public-distribution** corpus. The records inherit the public posture of the regulatory extracts they come from — the source agencies publish these under their own legal frameworks. No patient free-text narrative fields are carried; the structured, coded fields only.

If you find content in a record that re-identifies an individual **beyond what the source database itself already publishes**, that is a redaction-pass bug — please open an issue so it can be fixed.

This corpus is **not HIPAA-certified**, and parties using it retain their own privacy obligations.

---

## Snapshot in time

The corpus is **frozen at the snapshot date in the manifest** *(confirm date)*. The underlying regulatory databases keep updating — reports are added, and prior reports are sometimes revised silently between releases (severity reclassifications, recodings, follow-up outcomes added months later, lot corrections, occasional withdrawals). Any finding drawn from this corpus should **cite the snapshot date.**

## Known limitations

- **Cross-jurisdictional harmonization is lossy at the margins.** Different schemas, reporting cultures, and field semantics mean some records do not survive translation to the common schema; those are summarized in aggregate, not silently dropped.
- **Reporting behavior is a confound.** Volume reflects attention and reporting culture as much as anything clinical. Counts track *who reported,* not *what happened.*

---

## Use, attribution, and redistribution

You may share the corpus, this README, and the manifest. Please:

- Keep the corpus together with this README and its caveats.
- Preserve the manifest snapshot date in any onward citation.
- Mark any re-derived or re-aggregated data clearly as **derivative**, not attributed to the original corpus.

**License:** *[choose before publishing — e.g. CC BY 4.0 for the data/text, MIT or Apache-2.0 for any code. Until set, the corpus is provided **as is**, without warranty of any kind; in no event is the project or its contributors liable for any claim or damages arising from its use.]*

---

## Contact

- **Report a problem** (a redaction bug, a reproducibility failure, a harmonization error): open an issue on this repository — that is exactly the scrutiny this corpus is built to invite.
- **Project:** Meridian North · open, reproducible, public-interest data.

*If it holds, your run is one more independent verification. If you find a flaw, you've improved a tool that's free for everyone.*
