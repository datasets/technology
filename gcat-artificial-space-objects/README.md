# GCAT: General Catalog of Artificial Space Objects

Structured dataset derived from Jonathan McDowell's GCAT catalog of artificial space objects launched since 1957.

## Overview

This repository contains a cleaned tabular extract of GCAT's `satcat` dataset, plus an annual aggregate used for visualization.

- Dataset name: `gcat-artificial-space-objects`
- Coverage: 1957 to present (based on available source records)
- Current status: `structured`
- Primary source: https://planet4589.org/space/gcat/

## Files

- `datapackage.json`: dataset metadata, resource schemas, and chart view
- `data/satcat.csv`: cleaned object-level catalog (`68,140` data rows)
- `data/objects_per_year.csv`: yearly object counts by type (`70` data rows)
- `scripts/clean.py`: transformation script from raw GCAT TSV to cleaned CSV
- `TASK.md`: wrangling task brief

## Source and update note

- Source data endpoint: https://planet4589.org/space/gcat/data/cat/satcat.tsv
- Source catalog homepage: https://planet4589.org/space/gcat/
- Local processing date in this repo: **2026-03-14**

GCAT is maintained by Jonathan McDowell and updated over time. Re-running the pipeline may produce different row counts and values as the upstream catalog changes.

## Key fields (`satcat.csv`)

- `jcat`: GCAT object identifier
- `satcat`: NORAD catalog number (when available)
- `name`: object name
- `launch_date`: launch date (ISO-like best effort)
- `launch_year`: extracted year for aggregation
- `object_type`: simplified type (`Payload`, `Rocket Body`, `Debris`, `Component`, `Suborbital Payload`, `Unknown`)
- `state`: owning country/organization code
- `owner`: owning agency/organization code
- `status`: simplified mission/orbital status
- `orbit_class`: orbit class code from GCAT
- `perigee_km`, `apogee_km`, `inclination_deg`: orbital parameters (when known)

## Example use cases

- Trend analysis of launch activity by decade
- Comparing payloads vs debris growth over time
- Country-level historical launch profiling
- Orbit regime analysis using `orbit_class`

## Notes on cleaning

The transform script:

- strips GCAT comment/header metadata from raw TSV
- normalizes key fields into a publishable CSV schema
- maps GCAT type/status codes into simplified analysis-friendly labels
- keeps unknown/partial values as blank where parsing is not reliable

## License

`datapackage.json` declares `ODC-PDDL-1.0`.
