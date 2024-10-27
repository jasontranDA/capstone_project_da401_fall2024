# Capstone Project DA401 - Fall 2024

### Author: Jason Tran  
**Institution: Denison University**  
**Repository Name**: `capstone_project_da401_fall2024`

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Research Question](#research-question)
3. [Data](#data)
4. [Methodology](#methodology)
5. [Results](#results)
6. [Repository Structure](#repository-structure)
7. [Instructions for Reproduction](#instructions-for-reproduction)
8. [Acknowledgments](#acknowledgments)

---

## Project Overview

This repository contains the code and data for the DA401 Capstone Project for Fall 2024. The purpose of the research is to evaluate the impact of California’s cap-and-trade program on household gasoline expenditures, employing a Difference-in-Differences (DiD) approach to assess the changes over time between the pre-tax and post-tax periods.

The main focus of the study is to understand how household gasoline expenditures have evolved post the implementation of the cap-and-trade policy and to identify the varying impacts across gender and urban/rural households.

---

## Research Question

**How has California's carbon pricing policy affected household gasoline expenditures, particularly focusing on differential impacts across demographics (e.g., gender and urban/rural status)?**

### Hypothesis
- The cap-and-trade policy is expected to reduce gasoline expenditures, with heterogeneous effects across demographics.

---

## Data

The research leverages publicly available datasets to conduct the analysis, including:

1. **Consumer Expenditure Survey (CEX)**:
   - The **CEX** data provides detailed expenditure data on households. The analysis specifically uses variables related to demographics and gasoline expenditure.

2. **California Gasoline Prices**:
   - Obtained from the **Energy Information Administration (EIA)**, this dataset captures average gasoline prices over different periods, which is essential for comparing pre- and post-cap-and-trade impacts.

3. **Merged Datasets**:
   - The final merged dataset (`merged_datasets_California.csv`) combines the CEX data with California gasoline prices. This merged data serves as the primary dataset for running the econometric models.

#### Data Accessibility
- The raw data used for cleaning, merging, and analysis can be accessed via:
  - **CEX Data**: [Consumer Expenditure Survey](https://www.bls.gov/cex/)
  - **California Gas Prices**: [Energy Information Administration](https://www.eia.gov/)

- The cleaned and merged dataset is included in the `data/` folder of this repository for reproduction purposes.

- For more details about the variables, please refer to the **`dataset_instructions.md`** in the **`docs/`** folder.

---

## Methodology

This research utilizes the **Difference-in-Differences (DiD)** econometric technique to evaluate the impact of the cap-and-trade policy on household gasoline expenditures. The DiD approach compares changes over time (pre- and post-cap-and-trade) between different groups:

- **Treatment Group**: Households in California after the cap-and-trade policy implementation.
- **Control Group**: Households in California before the policy implementation.

This approach helps in isolating the impact of the policy while accounting for unobserved time-invariant differences. Interaction terms are used to evaluate heterogeneous effects based on gender and urban/rural status.

**Data Cleaning**: Mean imputation was used for missing values, and random imputation was applied for binary categorical variables such as gender and urban/rural status.

**Key Variables**:
- **Dependent Variable**: `gasoline_expenditure` (in dollars)
- **Independent Variables**: `post_tax_period`, `gender`, `urban_rural_status`, `fsize` (household size), `average_gas_price`, `income_level_poverty`
- **Interaction Terms**: `post_tax_period x gender`

---

## Results

The analysis reveals the following:

- **Impact of Post-Tax Period**: Household gasoline expenditures decreased by approximately $35 post the cap-and-trade policy implementation, suggesting a decrease in gasoline consumption.
- **Gender Analysis**: Female-headed households show approximately $4 less in gasoline expenditures than male-headed households, with the interaction term indicating a differential impact in post-tax periods.
- **Urban vs. Rural**: Urban households tend to spend $10 more on gasoline compared to rural households.
- **Price Sensitivity**: The average gasoline price coefficient indicates that households tend to maintain gasoline consumption levels despite price increases, reflecting inelastic demand.

The findings suggest that while the cap-and-trade policy might contribute to reduced gasoline consumption, the impact is not uniform across all household types.

For more in-depth analysis and visualization, please see the `results/` folder and the corresponding RMarkdown file.

---

## Repository Structure

The repository follows a structured layout to ensure reproducibility:

├── data/ │ ├── merged_datasets_California.csv │ └── ... (links to external sources for raw data) ├── docs/ │ ├── dataset_instructions.md │ └── methodology_details.md ├── notebooks/ │ ├── data_cleaning.Rmd │ ├── exploratory_analysis.Rmd │ └── econometrics_analysis.Rmd ├── results/ │ ├── regression_results.html │ ├── marginal_effects_plots.png │ └── summary_statistics.html ├── scripts/ │ ├── data_preprocessing.R │ ├── econometrics_modeling.R │ └── visualization.R └── README.md

- **`data/`**: Contains the cleaned and merged dataset.
- **`docs/`**: Holds detailed instructions about the dataset and methods used.
- **`notebooks/`**: Jupyter and RMarkdown notebooks for data cleaning, EDA, and econometrics modeling.
- **`results/`**: Contains outputs such as regression tables, plots, and summaries.
- **`scripts/`**: R scripts for various stages of the data processing and analysis.

---

## Instructions for Reproduction

To replicate the research results, follow these steps:

1. **Clone the Repository**:
git clone https://github.com/jasontranDA/capstone_project_da401_fall2024.git
2. **Setup Environment**:
- Ensure you have R and required R packages installed. You can install required packages using:
  ```R
  install.packages(c("data.table", "dplyr", "ggplot2", "stargazer", "margins", "kableExtra"))
  ```

3. **Run Scripts**:
- Start with running the data cleaning script:
  ```
  Rscript scripts/data_preprocessing.R
  ```
- Follow up with exploratory analysis and modeling using the notebooks in `notebooks/`.

4. **View Results**:
- Check the `results/` folder for output visualizations and regression results.

For any questions or clarifications, consult the **`dataset_instructions.md`** in the `docs/` folder.

---

## Acknowledgments

This project is carried out as part of the DA401 Capstone at **Denison University** under the guidance of the **Data Analytics** faculty. Special thanks to the **California Energy Commission** and the **Consumer Expenditure Survey** for providing the datasets used.

---


