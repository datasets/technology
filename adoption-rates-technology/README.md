# Technology Adoption Rates in the United States

Technology waves are getting faster.

In this dataset, telephone adoption rises over most of the twentieth century and takes roughly 80 years to move from early penetration to near-saturation in US households. Smartphone adoption reaches majority usage in about a decade.

## Dataset

- Primary file: `data/adoption_rates.csv` (long format)
- Chart helper file: `data/adoption_rates_wide.csv` (wide format for multi-series chart view)
- Columns:
  - `year` (integer)
  - `technology` (slug)
  - `adoption_pct` (percent on a 0 to 100 scale)
- Geography: United States only
- Technologies:
  - `telephone`
  - `radio`
  - `television`
  - `personal-computer`
  - `internet`
  - `mobile-phone`
  - `smartphone`

## Method

1. Downloaded OWID technology adoption series for the United States.
2. Filtered the series to target technologies.
3. Normalized names to slug format.
4. Wrote a long-format CSV with `year,technology,adoption_pct`.

## Sources

- Our World in Data, Technology Adoption page: https://ourworldindata.org/technology-adoption
- OWID grapher dataset used for wrangling: https://ourworldindata.org/grapher/technology-adoption-by-households-in-the-united-states.csv
- Our World in Data datasets repository: https://github.com/owid/owid-datasets
- US Census Historical Statistics reference: https://www.census.gov/library/publications/1975/compendia/hist_stats_colonial-1970.html
- Pew Research Center reference: https://www.pewresearch.org/
- ITU reference: https://www.itu.int/

## Notes

- This version uses OWID series values as the primary harmonized source for all included technologies.
- Coverage varies by technology and is constrained by source availability.
