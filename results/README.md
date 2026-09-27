# Results summary

This file summarises the recorded outputs from the
[analysis notebook](../notebooks/uk_weather_trends_analysis.ipynb). See the
notebook for the full methodology, visualisations and station-level results.

## Selected figures

- [`all_station_temperature_trends.png`](all_station_temperature_trends.png):
  fitted station trends with original residual-bootstrap intervals.
- [`temperature_station_comparison.png`](temperature_station_comparison.png):
  monthly maximum-temperature records for Heathrow, Lerwick and Braemar.
- [`heathrow_august_2075_interval.png`](heathrow_august_2075_interval.png):
  Heathrow's model-based August 2075 extrapolation against its historical
  August distribution.

## Dataset

- 39,427 monthly observations
- 37 UK weather stations
- Records spanning 1853–2025, with different coverage periods by station

## Maximum-temperature trends

All 37 station-level seasonal-linear models produced positive fitted trends.
The estimated slopes ranged from approximately **0.060°C to 0.502°C per
decade**.

| Station | Fitted trend | Original residual-bootstrap interval |
|---|---:|---:|
| Heathrow | +0.313°C per decade | 0.266 to 0.360°C per decade |
| Lerwick | +0.067°C per decade | 0.045 to 0.090°C per decade |

The intervals come from the original independent-residual bootstrap. Monthly
weather observations may be serially correlated, so these intervals should not
be interpreted as autocorrelation-robust inference.

## August 2075 model extrapolations

| Station | Extrapolated mean | Residual-bootstrap interval |
|---|---:|---:|
| Heathrow | 24.86°C | 21.70–28.25°C |
| Lerwick | 14.61°C | 12.54–16.65°C |

These are long-range extensions of the fitted linear models, not climate-model
projections or operational forecasts. Heathrow's interval overlaps its
historical August range, while Lerwick's lies almost entirely within its
historical range.

## Exploratory frost screening

- 5 of 37 winter decade-by-frost tests had raw p-values below 0.05.
- 2 stations—Valley and Stornoway—remained below 0.05 after either Bonferroni
  or Benjamini–Hochberg correction.
- 35 of 37 winter tables had at least one expected cell below 5.
- All 37 whole-year tables had at least one expected cell below 5.

The sparse expected counts weaken the chi-square approximation. These p-values
are exploratory signals for follow-up and do not establish the direction,
magnitude or cause of changes in frost occurrence.
