# Data Dictionary for DA 401 Capstone Project - Fall 2024

This data dictionary provides descriptions of all variables used in the DA 401 Capstone Project. The dataset examines household gasoline expenditures, using a Difference-in-Differences analysis to evaluate the impact of California's cap-and-trade policy.

## Variables in Dataset

| Variable Name           | Description                                                | Data Type   | Notes                                             |
|-------------------------|------------------------------------------------------------|-------------|---------------------------------------------------|
| `newid`                 | Unique identifier for each household                       | String      | Serves as a primary key                           |
| `year`                  | Year of the survey                                         | Integer     | Covers data from 2007 to 2021                     |
| `quarter`               | Quarter of the year                                        | Integer     | Values: 1, 2, 3, 4                                |
| `fsize`                 | Household size (number of individuals)                     | Numeric     | Number of individuals in the household            |
| `urbrur`                | Urban/Rural Status (1 = Rural, 0 = Urban)                  | Factor      | Indicates whether the household is urban or rural |
| `gender`                | Gender of household head (1 = Female, 0 = Male)            | Factor      | Indicates gender of the primary household head    |
| `fincbtxm`              | Household income before taxes (in dollars)                 | Numeric     | Reported in USD                                   |
| `educa2`                | Educational attainment of household head                   | Categorical | Various levels, from "Unknown" to "Doctorate"     |
| `gasoline_expenditure`  | Monthly expenditure on gasoline (in dollars)               | Numeric     | Measured in USD                                   |
| `average_gas_price`     | Average gasoline price per gallon (in dollars)             | Numeric     | Average price of gasoline within the surveyed area|
| `income_level_poverty`  | Income below poverty threshold (1 = Below, 0 = Above)      | Factor      | Based on US Census poverty thresholds             |
| `post_tax_period`       | Post-tax period indicator (1 = Post-Tax, 0 = Pre-Tax)      | Factor      | Differentiates pre- and post-cap-and-trade period |
| `popwt`                 | Population weight for household                            | Numeric     | Used for survey adjustments                       |

## Notes on Key Variables
- **`post_tax_period`**: Indicates the implementation of California’s cap-and-trade program. The Difference-in-Differences method relies on this variable to compare the outcomes before and after policy changes.
- **`income_level_poverty`**: Calculated based on household income compared to poverty thresholds. This is used to evaluate the impact of the policy on low-income households.
- **`gasoline_expenditure`**: Primary dependent variable, used to measure the changes in gasoline spending across the observed periods.
- **`gender`** and **`urbrur`**: Interaction terms are included to analyze the heterogeneous effects of gender and urban/rural status on gasoline expenditure.

## Data Cleaning
- Missing values in numeric variables were imputed using mean imputation.
- For binary variables such as `gender`, `urbrur`, and `income_level_poverty`, missing values were imputed through random sampling based on observed proportions.

## Data Quality and Limitations
- The use of mean imputation for missing continuous values may introduce bias if the data is not missing at random.
- The survey covers households only in California, which limits generalizability to other states.

---




