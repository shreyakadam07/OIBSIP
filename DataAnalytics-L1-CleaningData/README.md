Cleaning Data — Titanic Dataset

Track: Data Analytics (Level 1)<br> Internship: Oasis Infobyte SIP<br> Author: Shreya Kadam

📌 Objective

Take a deliberately messy dataset and systematically clean it into an analysis-ready dataset, documenting every decision made along the way.

🧰 Tech Stack
- Python
- pandas, numpy
- Jupyter Notebook
  
📂 Dataset

Titanic Dataset (Kaggle) — contains passenger details along with 19 junk placeholder columns (zero, zero.1–zero.18) and a typo'd target column (2urvived).

🔍 Approach

Data Quality Report — checked nulls, duplicates, data types, and column names before cleaning. <br>
Removed Junk Columns — dropped 19 meaningless zero-prefixed columns. <br>
Fixed Column Names — renamed 2urvived → Survived, standardized other column names. <br>
Missing Data Handling — filled numeric gaps with median, categorical gaps with mode. <br>
Duplicate Removal — identified and removed duplicate rows. <br>
Standardisation — checked categorical columns for inconsistent formatting. <br>
Outlier Detection — used the IQR method on Fare; retained outliers as genuine first-class fares. <br>
Data Type Correction — converted columns to appropriate types (category, int). <br>
Saved Cleaned Dataset — exported as titanic_cleaned.csv. 

📁 Files in This Folder
- data_cleaning_titanic.ipynb — full cleaning notebook
- README.md — this file
- titanic.csv — original dataset
- titanic_cleaned.csv — cleaned output
