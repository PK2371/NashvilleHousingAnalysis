# Nashville Housing Analysis

This project focuses on cleaning and transforming a dataset related to housing in Nashville. The data cleaning process involves standardizing formats, handling missing data, breaking down and restructuring fields, removing duplicates, and preparing the data for analysis.

## Table of Contents
- [Project Overview](#project-overview)
- [Key Steps in Data Cleaning](#key-steps-in-data-cleaning)
- [Technologies Used](#technologies-used)

---

## Project Overview
This project demonstrates how to clean and organize raw housing data for further analysis. The dataset includes details like property addresses, sale dates, sale prices, and more. The main objectives include:
- Cleaning and standardizing data formats.
- Populating missing information where possible.
- Restructuring data into more usable forms.
- Removing duplicates to ensure data integrity.
- Preparing the dataset for analysis.

---

## Key Steps in Data Cleaning

### 1. Standardizing Date Formats
- Converted raw date values into a consistent `YYYY-MM-DD` format using SQL's `CONVERT()` function.
- Added a new column `SaleDateConverted` for the cleaned date format.

### 2. Populating Missing Property Addresses
- Identified missing property addresses and used matching `ParcelID` records to fill them in.
- Applied the `ISNULL()` function for handling missing values during updates.

### 3. Breaking Out Address Components
- Split `PropertyAddress` into individual columns for street address (`PropertySplitAddress`) and city (`PropertySplitCity`).
- Applied similar logic to split the `OwnerAddress` into `OwnerSplitAddress`, `OwnerSplitCity`, and `OwnerSplitState`.

### 4. Standardizing `SoldAsVacant` Field
- Converted values in the `SoldAsVacant` field from `Y`/`N` to `Yes`/`No` for better readability using a `CASE` statement.

### 5. Removing Duplicates
- Used a Common Table Expression (CTE) with the `ROW_NUMBER()` function to identify and remove duplicate rows based on key columns (`ParcelID`, `PropertyAddress`, `SalePrice`, `SaleDate`, `LegalReference`).

### 6. Dropping Unused Columns
- Removed unnecessary columns such as `OwnerAddress`, `TaxDistrict`, and `PropertyAddress` to streamline the dataset.

---

## Technologies Used
- **SQL Server**: Used for all data transformations and cleaning processes.
- **T-SQL**: Transact-SQL syntax for querying and updating the database.

---
