# Dataset: epoch-data-on-ai-models

This is a [Frictionless Data Package](https://specs.frictionlessdata.io/data-package/).

## Concepts

**Data hierarchy** (from broad to specific):
- **Catalog** = a collection of datasets (maps to a DataHub publication, one GitHub repo)
- **Dataset** = a coherent data concept with a defined schema and coverage — this directory
- **Data file** = a concrete file artifact (csv, json, parquet…) listed as a resource in datapackage.json

**Dataset lifecycle** — a dataset doesn't need to be complete on day one:
- *capture* — just a URL or note, intent to explore
- *stub* — minimal entry: title, description, source link, no files yet
- *archived* — raw files downloaded locally
- *structured* — cleaned, normalised, schema documented
- *enriched* — analysis, visualisations, derived data added
- *monitored* — living source, versioned and updated over time

**Catalog-as-repo pattern**: if the source is a portal or collection containing many datasets (e.g. a data.gov agency, an institutional archive), give it its own repo and DataHub publication — not a subfolder here.

---

## Structure

```
epoch-data-on-ai-models/
  datapackage.json   # dataset metadata and resource list
  data/              # data files (csv, json, parquet, etc.)
  .datahubignore     # files to exclude when pushing (gitignore syntax)
```

## datapackage.json

Keep `resources` in sync with what's in `data/`:

```json
{
  "name": "epoch-data-on-ai-models",
  "title": "Human readable title",
  "description": "What this dataset is about",
  "resources": [
    {
      "path": "data/my-file.csv",
      "name": "my-file",
      "mediatype": "text/csv"
    }
  ]
}
```

## Workflow

```sh
# Add data files to data/
# Edit datapackage.json — update resources to list them
data pack .   # validate
dh push .     # publish to DataHub
```

## Key rules

- Every file in `data/` that you want published must be listed in `resources`
- `name` in datapackage.json must be URL-safe (lowercase, hyphens)
- Use `.datahubignore` to exclude scratch files, large intermediaries, etc.
- It is fine to push a stub — set lifecycle stage in `datapackage.json` as `"status": "stub"` if incomplete
