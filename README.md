# Spatial Joins Tutorial

This self-contained lesson teaches point-in-polygon spatial joins with a real point-location table and 2024 Census county, census tract, incorporated-place, and Census designated place boundaries.

The lesson is intentionally source-neutral. It focuses on reusable GIS concepts: coordinate validation, CRS alignment, spatial predicates, boundary-edge fallback logic, aggregation, join QA, and map-ready exports.

## Real-data notice

`data/point_locations.csv` contains real point coordinates, employee estimates, and revenue estimates and is included in this tutorial with project authorization. Names, addresses, and websites remain excluded because the lesson does not use them. If you adapt this lesson to another dataset, confirm that you have permission to share its point locations and attributes.

## Folder contents

```text
spatial_joins/
  spatial_join_lesson.ipynb
  requirements.txt
  data/
    README.md
    point_locations.csv
    counties_2024.geojson
    census_tracts_2024.geojson
    incorporated_places_2024.geojson
    census_designated_places_2024.geojson
  outputs/
```

## Run the lesson

Create or activate a Python environment, install the pinned dependencies, and start Jupyter from this folder:

```powershell
python -m pip install -r requirements.txt
python -m jupyter lab
```

For a noninteractive execution check:

```powershell
python -m jupyter nbconvert --execute --inplace --ExecutePreprocessor.timeout=600 spatial_join_lesson.ipynb
```

The notebook creates aggregate, QA, point-assignment, GeoJSON, and HTML outputs under `outputs/`.

Four industry tables provide one row per Census geography and industry code, sorted by `GEOIDFQ` and `industry_code`:

- `county_industry_employee_revenue.csv`
- `census_tract_industry_employee_revenue.csv`
- `incorporated_place_industry_employee_revenue.csv`
- `census_designated_place_industry_employee_revenue.csv`

Each contains point counts, summed employee estimates, summed available revenue estimates, and revenue coverage counts. Incorporated places and CDPs do not cover the whole state, so unmatched points are expected for those two levels.
