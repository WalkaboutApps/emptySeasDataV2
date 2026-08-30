# emptySeasDataV2

Depth-band vector tiles for [EmptyTheSeas](https://github.com/WalkaboutApps/emptytheseas),
built from [NOAA BlueTopo](https://nauticalcharts.noaa.gov/data/bluetopo.html).

Served over GitHub Pages, which honours HTTP Range requests, so the client reads
only the tiles near the observer rather than downloading a whole region.

| file | what |
|---|---|
| `*.pmtiles` | PMTiles v3 archive of MVT depth bands, z8–z13 |
| `*.meta.json` | contract version, level ladder, vertical datum, provenance |

## Contract

Elevation is **positive up**, as NOAA publishes it — sea floor is negative, the
shoreline is 0. Each polygon carries `elev_min` (deeper bound), `elev_max`
(shallower bound, where the terrace cap renders) and `band`, an index into
`level_ladder_m`. The client negates once for display.

Every polygon is guaranteed to triangulate under the shipping CDT build; that is
enforced by an exhaustive offline gate at build time, not discovered on device.

## Current coverage

San Francisco Bay only — 15 BlueTopo tiles at 4 m, UTM 10.

## Not this repo

v1 packages (GeoPackage regions, bought via IAP) live in `emptySeasData` and are
still served for clients already in the wild. Nothing here replaces those in place.

## Rebuilding

    python3.14 pipeline/bluetopo.py --bbox -122.55 37.70 -122.25 37.95 \
        --name "San Francisco Bay" --out build
