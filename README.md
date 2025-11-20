# SQL Project – Layoffs Data Cleaning

This project focuses on **cleaning and standardizing a real-world layoffs dataset** from Kaggle using SQL only.

Dataset source:  
[Layoffs 2022 – Kaggle](https://www.kaggle.com/datasets/swaptr/layoffs-2022)

The goal is to:

- Keep an untouched **raw copy** of the data
- Create a **staging layer** for cleaning
- Remove **duplicates**
- **Standardize** inconsistent values (industry, country, date format)
- Handle **NULLs** and **useless rows/columns**
- Produce a clean table ready for **EDA / analysis**

---

## Files in this Repo

- `layoffs.csv`  
  Raw dataset downloaded from Kaggle.

- `Data_Cleaning.sql`  
  Full SQL script that:
  - creates staging tables
  - removes duplicates
  - standardizes values
  - fixes date formats
  - deletes unusable rows/columns



