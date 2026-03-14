# Historical Adoption of Technology (CHAT)

Cross-country Historical Adoption of Technology dataset — an unbalanced panel covering adoption of 100+ technologies in 150+ countries from 1750 to 2008. Compiled by Diego Comin and Bart Hobijn at the National Bureau of Economic Research (NBER).

## Data

`data/chat.csv` — each row is a country-year observation. Technology columns contain adoption counts or units specific to each technology (e.g. subscriptions, km of railway, kWh of electricity).

Key fields:

| Field | Description |
|---|---|
| `country_name` | Country name |
| `year` | Year of observation |
| `cellphone` | Mobile/cellular telephone subscriptions |
| `telephone` | Fixed telephone lines |
| `internetuser` | Internet users |
| `computer` | Personal computers |
| `tv` | Television sets |
| `radio` | Radio receivers |
| `elecprod` | Electricity production (kWh) |
| `railline` | Railway lines (km) |
| `vehicle_car` | Passenger cars |
| `ag_tractor` | Agricultural tractors |
| `xlpopulation` | Total population |
| `xlrealgdp` | Real GDP |

See `datapackage.json` for the full schema with all 100+ technology columns.

## Source

[NBER — The CHAT Dataset (Comin & Hobijn, 2009)](http://www.nber.org/papers/w15319)

## License

[Open Data Commons Public Domain Dedication and License (ODC-PDDL)](https://opendatacommons.org/licenses/pddl/)
