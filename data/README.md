# Tutorial Data

These files are the complete runtime inputs for `spatial_join_lesson.ipynb`.

## `point_locations.csv`

Real point-location records prepared for spatial-join instruction.

- Rows: 62,749
- Coordinate-valid rows: 62,547
- Missing or invalid coordinate rows: 202
- CRS for usable longitude/latitude pairs: WGS 84 / EPSG:4326
- Included in this public tutorial with project authorization

Fields:

| Field | Meaning |
| --- | --- |
| `point_id` | Tutorial-safe sequential row identifier |
| `industry_code` | Detailed industry classification code retained as text |
| `industry_sector` | Broad industry-sector label |
| `industry_description` | Detailed industry label |
| `employee_count` | Record-level employee estimate used in aggregate outputs |
| `revenue` | Record-level revenue estimate; blank when unavailable |
| `longitude` | X coordinate in EPSG:4326 |
| `latitude` | Y coordinate in EPSG:4326 |

All 62,749 records have an employee value. Revenue is available for 40,798 records and missing for 21,951 records. Names, addresses, and websites are intentionally excluded because they are not needed for the lesson.

## Census boundary files

The four GeoJSON files are derived from U.S. Census Bureau 2024 TIGER/Line boundaries for West Virginia.

- Counties: 55 features
- Census tracts: 546 features
- Incorporated places: 231 features
- Census designated places: 208 features
- Delivery CRS: WGS 84 / EPSG:4326
- Join keys: `GEOID`, `GEOIDFQ`
- Label field: `NAMELSAD`

The boundary exports retain only the identifiers, name, boundary year, and geometry required by the lesson. County and tract polygons provide statewide coverage. Incorporated-place and CDP polygons cover named settlements only, so many valid points will not match either settlement layer.
