# Lithuania Administrative Divisions / Lietuva



## Overview

| Item | Details |
|------|---------|
| County | 10 |
| Municipality | 54 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/lt](https://openadmindata.org/lt/) |
| API | [openadmindata.org/api/lt](https://openadmindata.org/api/lt/) |
| Flag | [PNG](https://onlygames.me/flags-png/lt/) · [SVG](https://onlygames.me/flags-svg/lt/) · [PDF](https://onlygames.me/flags-pdf/lt/) |
| National Anthem | [🎵 Listen & Download Lithuania National Anthem MP3](https://onlygames.me/national-anthems/lt/) |

## Browse by County

| # | County | Municipalitys | Link |
|---|----|----|------|
| 1 | Telšiai (Telsiai) | 4 | [Browse](divisions/telsiai-lt01/) |
| 2 | Klaipeda | 6 | [Browse](divisions/klaipeda-lt02/) |
| 3 | Marijampole | 5 | [Browse](divisions/marijampole-lt03/) |
| 4 | Šiauliai (Siauliai) | 6 | [Browse](divisions/siauliai-lt04/) |
| 5 | Vilnius | 7 | [Browse](divisions/vilnius-lt05/) |
| 6 | Alytus | 4 | [Browse](divisions/alytus-lt06/) |
| 7 | Taurage | 4 | [Browse](divisions/taurage-lt07/) |
| 8 | Kaunas | 7 | [Browse](divisions/kaunas-lt08/) |
| 9 | Panevežys (Panevezys) | 5 | [Browse](divisions/panevezys-lt09/) |
| 10 | Utena | 6 | [Browse](divisions/utena-lt10/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-county.json](data/all-county.json) | JSON | All 10 county records |
| [all-municipality.json](data/all-municipality.json) | JSON | All 54 municipality records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-county.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['municipality']} municipalitys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-county.json", "utf-8"));
console.log(`Total: ${data.length} countys`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=county, 2=municipality |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{county-slug}/
```

Municipalitys are listed inline in each county's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-county links
- [Per-county data](docs/llms-full/) — Full data by county

## Citation

```
Lithuania Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/lithuania-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
