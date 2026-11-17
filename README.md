# Indego Bike Share: Extreme Weather & Ridership Analysis

## Project Overview

This project investigates how extreme weather conditions affect Indego bike-share ridership in Philadelphia. Using 2024–2025 trip records and NOAA daily weather data, I analyzed whether ridership declines differ by season, passholder type, bike type, and geographic location.

The goal was to identify which riders and areas are most affected by extreme weather and provide actionable recommendations for Indego's operations team.

## Research Questions

- How does extreme weather affect daily bike-share ridership across seasons?
- Are casual riders more sensitive to extreme weather than annual and monthly members?
- Do electric bikes experience smaller ridership declines than standard bikes?
- Do ridership patterns differ near Temple University Station and City Hall South compared to other stations?

## Data Sources

Three datasets were used:

1. **Indego Trip Data:** Quarterly trip records covering January 2024 through December 2025, containing trip dates, passholder types, bike types, and station information.
2. **Indego Station Data:** Station identifiers, locations, activation dates, and operational status.
3. **NOAA Weather Data:** Daily weather observations from Philadelphia International Airport, including temperature, precipitation, snowfall, and wind speed.

The original trip dataset contained 2,627,563 records. Following data cleaning and filtering, 2,413,947 trips were retained for analysis.

## Methodology

Using R, I performed data cleaning, transformation, aggregation, and exploratory data analysis.

Extreme weather days were identified using the following criteria:

- Temperature: Daily average temperature in the highest or lowest 5% of observations.
- Precipitation: Daily precipitation in the highest 5% of observations.
- Wind: Average daily wind speed in the highest 5% of observations.
- Snow: Any measurable snowfall.

To account for seasonal differences in normal ridership patterns, extreme weather days were compared against non-extreme days within the same season.

Ridership was then evaluated across passholder categories, bike types, and station proximity to Temple University Station and City Hall South.

## Key Findings

- **Seasonality:** Extreme weather reduced daily ridership in every season, with declines ranging from approximately 14% in summer to 40% in fall.
- **Weather Type:** Snow and cold produced the largest ridership declines (roughly 50%), followed by heavy precipitation and wind. Heat had the smallest effect.
- **Passholder Type:** Casual riders experienced declines 17–33 percentage points greater than members across weather categories.
- **Bike Type:** Standard bikes experienced declines 6–10 percentage points greater than electric bikes across weather categories.
- **Geographic Differences:** Stations near Temple University experienced the largest declines, while stations near City Hall South experienced the smallest. Differences were relatively modest compared to passholder and bike type differences.

## Recommendations

The findings suggest that casual riders are the most vulnerable group during extreme weather, particularly during cold and snowy conditions.

Indego could investigate targeted incentives or promotional campaigns to encourage casual riders to continue using the system during periods of extreme weather.

## Tools & Technologies

- R
- RStudio
- Quarto
- tidyverse
- dplyr
- ggplot2
- lubridate
- NOAA Climate Data

## Limitations

This study is observational and cannot establish that weather directly caused changes in ridership.

Additional limitations include:
- Only two years of trip data were analyzed.
- Weather observations came from a single airport weather station.
- Weather categories could overlap.
- Day of week, holidays, special events, and system changes were not controlled for.
- Short-duration trips were retained, potentially affecting comparisons between rider groups.

## Repository Contents

- `README.md` – Project overview, methodology, and findings.
- `Report/` – Quarto source document and rendered HTML report.
- `R/` – Analysis and data-processing scripts.
- `Plots/` – Visualizations generated during the analysis.
- `Data/` – Dataset documentation and instructions for obtaining the original data.

*Note: Raw trip datasets are not included in this repository due to their size. Refer to the data sources above to obtain the original files.*
