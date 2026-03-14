# Task: Wrangle GCAT Space Objects Dataset

## Objective

Download and clean data from Jonathan McDowell's GCAT (General Catalog of Artificial Space Objects) and publish it as a structured dataset.

## Source

- Homepage: https://planet4589.org/space/gcat/
- Data files: https://planet4589.org/space/gcat/data/
- The main catalog file is `satcat.tsv` — the full satellite catalog

## What to do

1. **Download the main catalog** from https://planet4589.org/space/gcat/data/cat/satcat.tsv
   - This is a TSV with a fixed-width header section (lines starting with `#`) followed by tab-separated data
   - Strip the header comment block, keep the column headers, save as `data/satcat.csv`

2. **Inspect and document the schema** — key fields include:
   - `JCAT` — Jonathan's catalog number (primary key)
   - `Satname` — satellite name
   - `Country` — country of origin
   - `LDate` — launch date
   - `Dest` — destination orbit type (e.g. LEO, GEO, MEO, HEO, SSO, Lunar, etc.)
   - `Status` — operational status (A=active, D=decayed, etc.)
   - `Type` — object type (P=payload, R=rocket body, D=debris)
   - `Mass` — mass in kg (where known)

3. **Clean the data**:
   - Convert to proper CSV with consistent quoting
   - Ensure dates are in ISO format (YYYY-MM-DD) where possible
   - Document any fields that have their own codebooks

4. **Update datapackage.json**:
   - Set `"status": "structured"`
   - Add the CSV as a resource with schema (field names and types)
   - Add a `views` entry for a bar chart of launches by year (group by launch year, count objects)

5. **Write README.md** — describe the dataset, the source, key fields, and example use cases

## File structure when done

```
gcat-artificial-space-objects/
  datapackage.json    # updated with resource + schema
  README.md           # dataset description
  data/
    satcat.csv        # cleaned catalog
  AGENTS.md
  TASK.md
  .datahubignore
```

## Notes

- The GCAT site has many sub-catalogs (launch vehicles, launch sites, etc.) — focus only on `satcat` for now
- McDowell updates GCAT regularly; note the download date in README.md
- Do NOT push to DataHub — leave that for the human operator
- Status field codes: A=active, AR=active reentry, D=decayed, DU=decayed unknown date, E=expelled from solar system, L=landed, M=maneuvering, N=new (not tracked), R=reentered, S=sample return, U=uncontrolled reentry
