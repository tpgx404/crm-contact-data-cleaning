
# CRM Contact Data Cleaning Pipeline

## Overview

This project demonstrates a Python-based data cleaning and quality-checking pipeline designed to prepare inconsistent customer contact data for use in a CRM system.

The pipeline processes raw customer records, standardizes inconsistent values, identifies missing and invalid information, checks for potential duplicates, and generates clean output files along with a data quality report.

## Problem Statement

Customer data collected from multiple sources often contains inconsistent formatting, missing values, invalid contact information, duplicate records, and inconsistent categorical values.

Poor-quality data can affect CRM operations, customer communication, reporting, and downstream analysis.

This project addresses these issues by creating a repeatable data preparation workflow that transforms raw contact data into a standardized dataset while preserving records that require further review.

## Project Workflow

1. Load raw customer contact data from CSV.
2. Explore the dataset and identify data quality issues.
3. Standardize text fields and categorical values.
4. Inspect email and phone-number quality.
5. Investigate potential duplicate customer records.
6. Validate the cleaned dataset.
7. Export CRM-ready data and quality-review files.

## Data Quality Issues Addressed

- Missing email and phone information
- Leading and trailing whitespace
- Inconsistent name capitalization
- Inconsistent email capitalization
- Inconsistent country names
- Inconsistent customer status values
- City-name variations
- Invalid or suspicious email formats
- Inconsistent phone-number formats
- Potential duplicate customer records
- Date-format inconsistencies

## Tech Stack

- Python
- Pandas
- NumPy
- Jupyter Notebook
- GitHub

## Project Structure

```text
crm-contact-data-cleaning/
│
├── data/
│   └── raw/
│       └── customer_contacts_dirty.csv
│
├── notebooks/
│   └── data_quality_analysis.ipynb
│
├── src/
│   └── cleaning.py
│
├── output/
│   ├── customer_contacts_cleaned.csv
│   ├── duplicate_review.csv
│   └── data_quality_report.txt
│
├── requirements.txt
├── .gitignore
└── README.md
```

## Cleaning and Standardization

The pipeline performs the following operations:

- Removes leading and trailing whitespace from text fields.
- Standardizes first and last name capitalization.
- Converts email addresses to lowercase.
- Standardizes country names.
- Normalizes customer status values.
- Standardizes known city-name variations.
- Inspects phone numbers for formatting inconsistencies.
- Preserves original date values during date-quality investigation.
- Identifies potential duplicate contacts for manual review.

## Validation

The cleaned data is checked for:

- Total record count
- Unique customer IDs
- Duplicate customer IDs
- Exact duplicate rows
- Missing values
- Status distribution
- Country distribution
- Potential duplicate email records

Records are not automatically deleted solely because they appear similar. Potential duplicates are exported separately for review to avoid incorrectly merging legitimate customers.

## Outputs

The pipeline generates:

- `customer_contacts_cleaned.csv` — standardized customer contact dataset
- `duplicate_review.csv` — records with repeated email addresses requiring investigation
- `data_quality_report.txt` — summary of cleaning and validation results

## Key Learning Outcomes

- Data profiling and exploratory data analysis
- Handling missing and inconsistent data
- Data standardization using Pandas
- Basic data quality validation
- Duplicate detection and review
- Building repeatable data preparation workflows
- Preparing data for downstream CRM systems

## Future Improvements

- Stronger country-specific phone-number validation
- More robust date-format detection and ambiguity handling
- Improved duplicate matching using multiple customer attributes
- Automated data-quality metrics and thresholds
- Modularizing the pipeline into reusable Python functions
- Integration with a CRM API or database

---

**Note:** This project uses synthetic customer data and is intended for educational purposes.
