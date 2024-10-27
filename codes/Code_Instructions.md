# DA 401 Capstone Project - Fall 2024

## Overview
This repository contains the Quarto document (`DA401_Capstone.qmd`) for the analysis of California's cap-and-trade policy impact on household gasoline expenditures. The analysis utilizes a Difference-in-Differences (DiD) econometric model to evaluate the effect of the post-tax period on expenditures, while accounting for other household characteristics.

## File Description
- **`DA401_Capstone.qmd`**: This is the primary analysis script for the project, including:
  - **Data Cleaning**: Processing Consumer Expenditure Survey (CEX) and California gas prices datasets.
  - **Exploratory Data Analysis**: Visual summaries of household income, gasoline expenditure, and other key variables.
  - **Econometric Modeling**: Difference-in-Differences model to estimate policy impact, including interactions between gender and the tax period.

## Key Analysis Components
- **Data Cleaning**: Conversion of CEX and California gas prices datasets into a merged dataset (`merged_dataset_California.csv`) after handling missing values and variable transformations.
- **Exploratory Data Analysis**: Visualizations including density plots, boxplots, and scatter plots to provide descriptive insights.
- **Econometric Model**: Difference-in-Differences with robust standard errors, Variance Inflation Factor (VIF) diagnostics, and a marginal effects analysis.

## Usage
1. Download the cleaned dataset `merged_dataset_California.csv` from the `data/` folder.
2. Use the `.qmd` script to reproduce the analysis, visualizations, and econometric models.

## Requirements
- R packages: `data.table`, `dplyr`, `ggplot2`, `stargazer`, `lmtest`, `margins`, among others.
- Quarto is required to render the `.qmd` file.

## Notes
- This analysis includes both exploratory and causal inference to understand the implications of California's cap-and-trade policy.
- The project adheres to the best practices in econometric modeling, including addressing multicollinearity and analyzing marginal effects.

For detailed documentation of the dataset, refer to `dataset_instructions.md`.
