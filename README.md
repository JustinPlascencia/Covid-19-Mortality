# COVID-19 Mortality Analysis by U.S. HHS Region

## Overview
This project analyzes disparities in COVID-19 mortality across U.S. HHS regions (1–10) using public data from the CDC and Google Open Source COVID-19 Data. We examine how age, race, and geography intersect to affect mortality rates, and we apply Decision Tree and Random Forest models to predict mortality across demographic groups.

## Key Findings
- **Age** and **location** were the strongest predictors of mortality.
- **Non-Hispanic American Indian / Alaska Native** populations had the highest model predictive performance (R² = 0.55 with Random Forest).
- Individuals >50 years old in Region 4 faced significantly higher mortality than those ≤11 in Region 9.

## Data Sources
- **CDC Mortality Data** (2021–2023) – suppressed counts where <20 deaths
- **Google Open Source COVID-19 Data** (2020–2022) – includes vaccinations, hospitalizations, government response

> **Note:** The overlapping date range is Jan 1, 2020 – Jan 7, 2022.

## Data Processing
- Cleaned and standardized both datasets using Python (Pandas, NumPy)
- Aggregated states into HHS regions (see definition below)
- Merged on state/year. NaN values set to empty (CDC suppression footnote respected)

## HHS Region Definitions
 1: Connecticut, Maine, Massachusetts, New Hampshire, Rhode Island, Vermont
* 2: New Jersey, New York
* 3: Delaware, District of Columbia, Maryland, Pennsylvania, Virginia, West Virginia
* 4: Alabama, Florida, Georgia, Kentucky, Mississippi, North Carolina, South, Carolina, Tennessee
* 5: llinois, Indiana, Michigan, Minnesota, Ohio, Wisconsin
* 6: Arkansas, Louisiana, New Mexico, Oklahoma, Texas
* 7: Iowa, Kansas, Missouri, Nebraska
* 8: Colorado, Montana, North Dakota, South Dakota, Utah, Wyoming
* 9: Arizona, California, Hawaii, Nevada
* 10: Alaska, Idaho, Oregon, Washington


## Methods
- Descriptive statistics
- Time series analysis
- Heatmaps (Seaborn)
- Hypothesis testing (SciPy)
- Machine learning: Decision Tree & Random Forest (scikit-learn)

## Results Summary
| Model | Demographic Group | R² Score |
|-------|------------------|-----------|
| Decision Tree | Non-Hispanic American Indian / Alaska Native | 0.51 |
| Random Forest | Same group | 0.55 |
| Decision Tree | Non-Hispanic Black | 0.42 |
| Random Forest | Non-Hispanic Black | 0.46 |

## How to Reproduce
1. Clone this repo
2. Install requirements: `pip install -r requirements.txt`
3. Run `python clean_data.py`
4. Run `python analysis.py`
5. See `notebooks/` for EDA notebooks
6. Download CDC Covid Death data from this link https://www.cdc.gov/nchs/state-stats/deaths/covid19.html

## Limitations
- CDC suppressed counts for subgroups with <20 deaths → many NaN values
- Datasets only overlap Jan 2020 – Jan 2022
- Socioeconomic status (SES) data not available

## Ethical Considerations
We analyzed race and age disparities with care, acknowledging that each data point represents a person who died. This work is intended to highlight systemic health disparities, not to blame communities. Long COVID and ongoing impacts are outside our scope.

## Authors
Justin Plascencia

## License
MIT
