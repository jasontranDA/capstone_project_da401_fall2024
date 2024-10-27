# Dataset Instructions for DA 401 Capstone Project - Fall 2024

This project involves multiple datasets, which have been used for the analysis and merged to create a final dataset. This document provides instructions on the datasets used, their sources, and how they were merged to create the final data for analysis.

## Datasets Overview

1. **California Gas Prices Dataset (`Cali_gas_prices.csv`)**
   - **Description**: This dataset contains historical gasoline price data for California. It includes gas prices for different years and quarters, helping to understand the effect of price changes on household gasoline expenditures.
   - **Columns**:
     - `Date`: Date of gas price observation (format: "Month Day, Year").
     - `Gas_prices`: The average price per gallon of gasoline (in USD).
   - **Usage**: The dataset was used to obtain the average gas prices by year and quarter to analyze how these prices affected gasoline expenditure.

2. **Consumer Expenditure Survey (CEX) Datasets**
   - **Description**: CEX datasets provide household expenditure data from the Consumer Expenditure Survey, focusing on variables such as household income, gasoline expenditure, and demographics.
   - **Files Included**:
     - **FMLI Files**: Family-level files used for demographic information such as household size, gender of household head, and income.
     - **MTBI Files**: Monthly expenditure files used for extracting specific expenditure types, such as gasoline.
   - **Columns**:
     - `newid`: Unique identifier for each household.
     - `year`: Year of the observation.
     - `quarter`: Quarter of the observation.
     - `fsize`: Household size.
     - `urbrur`: Urban or rural classification (1 = Rural, 0 = Urban).
     - `gender`: Gender of household head (1 = Female, 0 = Male).
     - `fincbtxm`: Household income before taxes.
     - `gasoline_expenditure`: Monthly expenditure on gasoline.
   - **Usage**: These datasets were cleaned, relevant variables were selected, and merged to prepare them for the final analysis.

3. **Final Merged Dataset (`merged_datasets_California.csv`)**
   - **Description**: The final dataset contains the merged information from the California Gas Prices dataset and the CEX datasets. This dataset is used for the Difference-in-Differences analysis to study the impact of California’s cap-and-trade program on household gasoline expenditures.
   - **Columns**:
     - All relevant columns from the California gas prices dataset and CEX datasets. Read `Data Dictionary` for more information.
     - `post_tax_period`: Indicator variable representing whether the period is post the implementation of California’s cap-and-trade policy (1 = Post-Tax, 0 = Pre-Tax).
     - `income_level_poverty`: Indicator variable for households below the poverty line (1 = Below, 0 = Above).

## Data Cleaning and Merging Instructions

The data cleaning and merging process involved several steps, as outlined below:

1. **Cleaning Individual Datasets**:
   - Load each dataset using R and perform the necessary data cleaning.
   - For the **California Gas Prices Dataset**:
     - Convert `Date` to year and quarter using `lubridate` functions.
     - Calculate the average gas price for each year and quarter.
   - For the **CEX Datasets**:
     - Select key variables, rename columns for consistency, and ensure variables have appropriate data types.
     - For missing values:
       - For numeric columns (e.g., income), mean imputation was used.
       - For categorical variables (e.g., gender, urban/rural), random imputation was used based on observed proportions.

2. **Merging Datasets**:
   - **Merge by Year and Quarter**: Join the cleaned **CEX** datasets with the **California Gas Prices Dataset** using `year` and `quarter` as keys.
   - The final merged dataset, **`merged_datasets_California.csv`**, contains all relevant information to perform the Difference-in-Differences analysis.

## Data Files Organization

All data files should be placed in the `data/` folder of the repository for easy access.

- **Data Folder Structure**:
  - `data/Cali_gas_prices.csv`: Contains the California gasoline prices.
  - `data/CEX_fmli_files/`: Folder containing all FMLI files.
  - `data/CEX_mtbi_files/`: Folder containing all MTBI files.
  - `data/merged_datasets_California.csv`: The final merged dataset for analysis.

## Usage Notes

- The **final merged dataset** (`merged_datasets_California.csv`) is the one used in the econometric analysis and is located in the `data/` folder.
- All datasets are in CSV format to ensure ease of access and processing.
- Make sure to adjust the file paths accordingly if running the code on a different system.

## Further Documentation

For more detailed steps on how each dataset was cleaned, merged, and analyzed, please refer to the **`data_cleaning_code.R`** file in the repository.

For questions or support, please reach out to the repository maintainer or refer to the GitHub issues section.

---

