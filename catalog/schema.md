# Catalog Schema

The UTF-8 CSV file papers.csv is an optional structured companion to the public list in [papers.md](../papers.md). DOI is the primary deduplication key; multi-value fields use semicolons.

| Field | Meaning |
| --- | --- |
| id | Stable local identifier, typically firstauthorYEAR_topic. |
| year | Publication year reported by CrossRef. |
| title, authors, journal, doi | Bibliographic metadata. DOI omits the DOI URL prefix. |
| region | Study area or case study. |
| proxy_or_method | Proxy, geochronology, model, or integrated method. |
| evidence_type | Role in the evidence chain, such as proxy calibration, regional reconstruction, or method review. |
| priority | A for direct evidence or calibration, B for a transferable case, and F for a foundational method or review. |
| abstract_status | available when a verified abstract is available, otherwise metadata-only. |
| metadata_source | Metadata source or sources. |
| last_checked | Metadata verification date in ISO 8601 form. |
| notes_file | Optional public English reading note. |

## Deduplication

Normalize DOIs to lowercase after removing any DOI URL prefix. If DOI is unavailable, compare normalized title and first author as a fallback. Prefer the more complete publisher record when merging sources.

## Evidence Discipline

Keep observations, calibration relationships, chronological constraints, model assumptions, and final elevation estimates distinct. Record preservation, non-equilibrium fractionation, moisture source or recycling, spatial representativeness, and age alignment as potential uncertainty sources. Do not infer numerical results from a title or abstract alone.
