# Data Cleaning _ PowerQuery

## Project Overview
This project demonstrates the process of cleaning, transforming, and preparing an Amazon International Apparel Sales dataset for analysis using Power Query. The dataset contains intentionally messy data, including missing values, inconsistent formats, and duplicates, allowing hands-on practice with key data cleaning techniques. The goal is to produce a clean, standardized dataset that can be used for sales analysis.

## Dataset Overview
The dataset contains transactional sales information with columns such as SKU, Size, Date, Gross Amount, Index, and Months. Key challenges included:

#### Missing Values:
- 1,040 rows lacked transactional data.
- 2,474 rows missing critical SKU information.

#### Categorical Value Inconsistencies:
- The Size column had a mix of alphabetical, numeric, extreme outliers  and special labels.

#### Formatting Issues:
- Trailing punctuation and excessive whitespace in SKU and Size.
- Concatenation errors.

#### Redundancy & Logic Errors:
- Index and Months columns were redundant.
- Gross Amount had rounding inconsistencies.
- Date column had mixed formats (MM/DD and DD/MM).

#### Data Corruption:
- Nearly half of the Date column failed standard parsing.

####Structural Inconsistencies:
-Dataset appeared to be multiple tables merged together, requiring separation and re-integration.

## Cleaning and Transformation Steps
#### 1. Import and Initial Transformation:
- Imported the raw CSV into Power BI and opened Power Query for transformation.
- Separated the dataset into two distinct tables based on index ranges to handle structural inconsistencies.
- Forced the Date column to recognize mixed formats (MM/DD vs DD/MM).
- Deleted redundant columns such as Month and Stock.

#### 2. Advanced Cleaning & Transformation:
- SKU Reconstruction: Filled missing SKUs by concatenating Style and Size columns.
- Table Alignment: Rearranged columns in the second table to match the first, ensuring consistent column order and font casing.
- Size Extraction: Added a Size column to the second table by extracting text after delimiters in the SKU field.

#### 3. Appending and Standardization:
- Appended the two cleaned tables into a single dataset.
- Standardized text formatting and corrected inconsistent values across the merged dataset.

#### 4. Duplicate Removal:
- Removed duplicate records using Date, Customer, and SKU as reference keys.

#### 5. Date Table Creation (Time Intelligence):
- Created a dedicated DateTable in Power BI using CALENDARAUTO().
- Generated additional columns for Month, Day of the Week, and Year to enable analysis of revenue and sales trends over time.

## Tools Used
- Power BI
- Power Query
- Excel


