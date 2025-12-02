# DagimFininsa_Final_Project

# Time to Treatment and Colorectal Cancer–Specific Survival (SEER 2016–2017)

## Project Description

This repository contains data and code for my Advanced Data Analysis final project. The goal is to evaluate whether time from colorectal cancer (CRC) diagnosis to first treatment is associated with CRC-specific survival among adults diagnosed in SEER 2016–2017. I use Kaplan–Meier methods and Cox proportional hazards models to estimate survival across time-to-treatment categories (0–30, 31–59, 60–89, 90+ days), adjusting for key demographic and clinical characteristics.

## Files Included

- `CRC_SEER_TImetoTreatment.csv`  
  Original SEER extract used for the project. This file contains all eligible CRC cases before any cleaning, exclusions, or variable recoding.

- `seer_analytic_ttt_crc.csv`  
  Cleaned analytic dataset created from `CRC_SEER_TImetoTreatment.csv`. This file includes:
  - Derived time to treatment categories  
  - Follow up time and CRC specific death indicator  
  - Recoded variables for age group, sex, race, stage, rurality, and treatment type  
  - Only observations that met all inclusion criteria for the analysis  
- `survival_analysis.Rmd`  
  R Markdown file that imports the data, performs data cleaning, generates descriptive tables, and fits survival models.

- `README.md`  
  This file.

## What the Code Does

The main steps in `survival_analysis.Rmd` are:

- Reads in the SEER analytic dataset (`CRC_SEER_TImetoTreatment.csv`).  
- Recodes and labels variables (age group, sex, race, rurality, stage, treatment timing).  
- Creates descriptive statistics for the overall cohort and by time-to-treatment category.  
- Fits Kaplan–Meier survival curves and performs log-rank tests.  
- Fits multivariable Cox proportional hazards models to estimate hazard ratios for CRC-specific death across time-to-treatment categories, adjusting for covariates.  
- Exports publication-ready tables and figures (HTML tables and PNG survival plot).

## How to Run the Code

1. Download or clone this repository to your computer.  
2. Open `survival_analysis.Rmd` in RStudio.  
3. Make sure your working directory is the folder that contains `CRC_SEER_TImetoTreatment.csv`.  
4. Install any missing packages listed at the top of the Rmd (for example: `tidyverse`, `survival`, `survminer`, `gtsummary`).  
5. Click **Knit** to run the full analysis and recreate all tables and figures.

## Software and Version

- R version: 4.4.1  
- RStudio: 2025.9.2.418

## Author

- Name: Dagim Fininsa  
- Course: Advanced Data Analysis (Final Project)  
- Date: December 2025
```
