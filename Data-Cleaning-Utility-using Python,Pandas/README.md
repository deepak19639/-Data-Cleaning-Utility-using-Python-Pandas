
# 🧹 Data Cleaning Utility – Python (Pandas)

A simple yet powerful data cleaning project using Python and Pandas. This tool reads a raw CSV file, handles common data quality issues, and saves a clean version ready for ETL or analysis.

---

## 📌 Objective

To clean raw sales data by:

- Removing null values
- Dropping duplicate rows
- Standardizing column names and string values
- Ensuring correct data types
- Saving the cleaned data to a new CSV file

---

## 📂 Folder Structure

```
Data-Cleaning-Utility/
│
├── README.md                      ← Project overview and steps
│
├── data/
│   ├── raw_data.csv               ← Original raw CSV file (sample_sales_data.csv)
│   └── clean_data.csv             ← Cleaned output file
│
├── notebook/
│   └── data_cleaning.ipynb        ← Colab notebook with complete logic
│
│
└── report/
    └── Data_Cleaning_Report.docx  ← Word report with all screenshots and steps
```

---

## 🚀 Steps Performed in Notebook

### 1. 📥 Import CSV & View Data
```python
import pandas as pd
from google.colab import files

uploaded = files.upload()
df = pd.read_csv('sample_sales_data.csv')
df.head()
```

---

### 2. ❓ Handle Null Values
- Detected nulls using `df.isnull().sum()`
- Removed rows with missing critical fields:
```python
df = df.dropna(subset=['City', 'Purchase Amount', 'Rating'])
```

---

### 3. 🔁 Remove Duplicates
```python
df = df.drop_duplicates()
```

---

### 4. 🧹 Standardize Column Names
```python
df.columns = df.columns.str.lower().str.strip().str.replace(' ', '_')
```

---

### 5. ✂️ Standardize String Values
Example – lowercase & strip whitespaces in `City` column:
```python
df['city'] = df['city'].str.lower().str.strip()
```

---

### 6. 🧠 Standardize Data Types
Ensured numeric and datetime columns were correctly parsed.

---

### 7. 💾 Save Cleaned File
```python
df.to_csv('clean_data.csv', index=False)
```

---

## 📸 Screenshots

- See the `/screenshots` folder or `Data_Cleaning_Report.docx` for visuals of each step.

---

## 🧑‍💻 Tools Used

- Python 3 (Google Colab)
- Pandas Library

---

## 🏁 Output

A cleaned CSV file that is ready to be used in Data Engineering pipelines or analytics workflows.

---

## 🧠 Author

**Deepak Kumar**  
_Data Engineering Aspirant | Skilled in SQL, EDI, Python, and Data Pipelines_

---
