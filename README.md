# SWYNEX-Data-Cleaning-Preparation
# SWYNEX Task 1: Data Cleaning & Preparation

## Project Overview
This project focuses on auditing, cleaning, and standardizing a messy raw hospital patient dataset containing administrative, clinical, and billing records.

## Repository Contents
* `raw_hospital_data.csv`: Original uncleaned dataset (970 records).
* `cleaned_hospital_data.xlsx`: Fully cleaned and sorted dataset with feature additions (950 records).

## Data Cleaning & Transformation Performed
1. **Deduplication:** Identified and eliminated 20 duplicate patient entries, bringing total records from 970 to 950.
2. **Text Standardization & Typos:**
   * **Gender:** Standardized inconsistent labels (`M`, `Male`, `F`, `Female`, `Femael`) into uniform `Male` and `Female` categories.
   * **Room Type:** Corrected misspellings (`Generel` → `General`) and inconsistent casing (`semi` → `Semi-Private`).
   * **Feedback:** Standardized typos and case variations (`averge` → `Average`, `good` → `Good`).
3. **Missing Value Imputation:**
   * Handled missing `Age` values by imputing the median value (43).
   * Filled blank `Diagnosis` records with `Unspecified`.
   * Filled missing `Feedback` fields with `Not Provided`.
4. **Data Types & Feature Engineering:**
   * Formatted `Admission_Date` and `Discharge_Date` to valid standard date formats.
   * Derived **`Length_of_Stay`** (`Discharge_Date - Admission_Date`) to measure total patient stay duration.
   * Extracted **`Admission_Month`** for temporal trend analysis.
5. **Sorting:** Sorted the final clean dataset sequentially by `Patient_ID` in ascending order.
