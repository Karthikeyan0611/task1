# 🧹 Data Cleaning Script

This repository contains a Python script used to clean a dataset (`your_dataset.csv`) using **Pandas** and **SciPy**. The script handles missing values, duplicates, standardizes column names and formats, and removes outliers.

## 📁 Input

- **your_dataset.csv**: Raw dataset file to be cleaned (should be placed in the same directory as the script).

## 📄 Overview of Cleaning Steps

The following data cleaning tasks are performed:

### 1. 📊 Initial Inspection
- Prints the initial shape and preview of the dataset.
- Displays data types and non-null counts using `.info()` and `.head()`.

### 2. 🔧 Handling Missing Values
- **Numerical Columns**: Missing values are filled with the **mean** of each column.
- **Categorical Columns**: Missing values are filled with `"Unknown"`.

### 3. 🧼 Removing Duplicates
- Duplicate rows are dropped from the dataset.

### 4. 👤 Gender Standardization
- If a `gender` column exists:
  - Strips whitespaces, converts to lowercase.
  - Maps `'m'` → `'male'` and `'f'` → `'female'`.

### 5. 🗓 Date Parsing
- If a `signup_date` column exists:
  - Converts to `datetime` format.
  - Invalid formats are coerced to `NaT`.

### 6. 🧾 Column Name Standardization
- Converts column names to:
  - Lowercase
  - Underscore-separated
  - Whitespace trimmed

### 7. 🔢 Age Handling
- If `age` column exists:
  - Fills missing values with `0`.
  - Converts to integer type.

### 8. 📉 Income Outlier Removal
- If `income` column exists:
  - Applies **Z-score filtering** (removes rows where z-score of income ≥ 3).

### 9. ✅ Output
- Final shape and info are printed.
- Cleaned data is saved to `cleaned_dataset.csv`.

## 🛠 Dependencies

- Python 3.x
- pandas
- scipy

You can install the required libraries using:

```bash
pip install pandas scipy
