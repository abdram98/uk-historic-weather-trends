# Data

This directory contains the historical station-data snapshot used in the
analysis.

## Contents

```text
data/
├── README.md
├── ATTRIBUTION.md
└── raw/
    └── weather_data/
        ├── ALL-WEATHER-STATIONS.csv
        ├── aberporthdata.csv
        ├── armaghdata.csv
        └── ... 35 additional station files
```

`ALL-WEATHER-STATIONS.csv` contains station names, coordinates and coverage
dates. The other 37 files contain monthly observations with these fields:

- `Year`
- `Month`
- `TMax`: mean daily maximum temperature in °C
- `TMin`: mean daily minimum temperature in °C
- `Frost`: number of air-frost days
- `Rainfall`: total rainfall in mm
- `Sunshine`: total sunshine duration in hours
- `Status`: confirmed or provisional observation status

The snapshot contains 39,427 station-month rows. Station coverage varies, with
some series beginning in the nineteenth century and the latest records dated
2025.

For integrity checking, the SHA-256 digest of the alphabetically ordered list
of individual CSV SHA-256 digests is:

```text
61b9e2ee53eeb9f0093e71eb67426df8457c9b823b91d4926d5286b8a9b82fe4
```

Recalculate it from the `data/` directory with:

```bash
shasum -a 256 raw/weather_data/*.csv | shasum -a 256
```

## Source

The source is the UK Met Office
[historic station collection](https://www.metoffice.gov.uk/research/climate/maps-and-data/historic-station-data).
The [official dataset catalogue](https://www.data.gov.uk/dataset/17ba3bbe-0e98-4a8c-9937-bd1d50fdc3c5/historic-monthly-meteorological-station-data)
describes the 37-station monthly dataset and its licence.

## Important caveats

- Station records cover different time periods.
- Some recent observations are provisional.
- The Met Office states that no allowances have been made for small site
  changes or developments in instrumentation.
- Missingness differs between variables and stations.

See [`ATTRIBUTION.md`](ATTRIBUTION.md) for reuse terms.
