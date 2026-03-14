# Task: Wrangle Technology Adoption Rates Dataset (da-jui)

You are wrangling a dataset of technology adoption rates over time for publication on DataHub under the `technology` publication.

## Goal

Build `data/adoption_rates.csv` with US adoption rates for key technologies over time.

## Schema

```
year,technology,adoption_pct
1920,radio,0.1
```

Fields:
- `year`: integer year
- `technology`: slug name (telephone, radio, television, personal-computer, internet, mobile-phone, smartphone)
- `adoption_pct`: share of US households (or population) using the technology (0–100 scale)

## Technologies to cover

| Technology | Expected coverage |
|------------|------------------|
| telephone | ~1900–present |
| radio | ~1920–present |
| television | ~1950–present |
| personal-computer | ~1980–present |
| internet | ~1990–present |
| mobile-phone | ~1990–present |
| smartphone | ~2007–present |

## Sources

- Our World in Data "Technology Adoption" page and underlying data: https://ourworldindata.org/technology-adoption
- OWID GitHub data repo: https://github.com/owid/owid-datasets
- US Census Historical Statistics: https://www.census.gov/library/publications/1975/compendia/hist_stats_colonial-1970.html
- Pew Research Center (internet/mobile/smartphone)
- ITU (mobile/internet)

## Steps

1. Fetch OWID technology adoption data (check their GitHub or data API)
2. Filter to United States, key technologies listed above
3. Normalise to schema above
4. Write `data/adoption_rates.csv`
5. Update `datapackage.json`: set `status` to `structured`, add resource, add a line chart view
6. Write `README.md` — lead with the story: each technology wave is adopted faster than the last (telephone took ~80 years to reach saturation; smartphone took ~10). No tilde (~) characters.

## Constraints
- No tilde characters in README.md (breaks MDX rendering)
- adoption_pct as 0–100 (percent, not decimal)
- US only for consistency
- Do NOT push — owner will push manually
