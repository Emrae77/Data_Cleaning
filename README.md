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

---

## Tech Stack / Assumptions

- SQL dialect: **MySQL 8+** (or compatible, e.g. MariaDB with window functions)
- Database/schema name: `world_layoffs`
- Raw table name: `world_layoffs.layoffs`

The script uses:

- `ROW_NUMBER() OVER (...)` window function  
- CTEs (`WITH ... AS`)  
- MySQL functions like `STR_TO_DATE`, `TRIM`, `UPDATE ... JOIN ...`

---

## High-Level Cleaning Steps

The cleaning process happens in **staging tables** so the raw data is never touched.

### 1. Create a Staging Copy

```sql
CREATE TABLE world_layoffs.layoffs_staging 
LIKE world_layoffs.layoffs;

INSERT world_layoffs.layoffs_staging 
SELECT * FROM world_layoffs.layoffs;
