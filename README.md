# Retail Sales Exploratory Data Analysis (EDA) and predictive modeling


## Overview
A two-part project series covering Exploratory Data Analysis (Project #1) and Machine Learning Regression (Project #2) on a retail sales dataset of 1,000 transactions.

## 📁 Repository Structure

```
CS667-RetailSales/
│
├── Project1_EDA/
│   ├── CS667_Project1_EDA.ipynb          # EDA notebook (8 sections)
│   └── README_P1.md
│
├── Project2_ML/
│   ├── CS667_Project2_RetailSales.ipynb  # ML regression notebook (Colab ready)
│   └── CS667_Project2_Report.docx        # Written report
│
├── retail_sales.xlsx                      # Shared dataset (both projects)
└── README.md                              # This file
```

---

## Part-1(EDA) Overview

This project performs a comprehensive Exploratory Data Analysis on a retail sales dataset containing 1,000 transactions across three product categories (Beauty, Clothing, Electronics). The goal is to uncover patterns, identify key drivers of sales, and generate actionable business insights.

## Dataset

| Attribute | Detail |
|-----------|--------|
| **File** | `retail_sales.xlsx` |
| **Records** | 1,000 transactions |
| **Date Range** | Jan 2023 – Jan 2024 |
| **Columns** | 9 |

**Columns:** Transaction ID, Date, Customer ID, Gender, Age, Product Category, Quantity, Price per Unit, Total Amount

## Project Structure

```
├── CS667_Project1_EDA.ipynb          # Main Jupyter Notebook (8 sections)
├── retail_sales.xlsx                 # Source dataset
└── README.md
```

## Notebook Sections

1. **Setup & Data Loading** – Import libraries, load Excel data
2. **Data Overview** – Shape, dtypes, first/last rows, descriptive statistics
3. **Data Quality Check** – Missing values, duplicates, data type validation
4. **Univariate Analysis** – Distribution of Age, Quantity, Price per Unit, Total Amount
5. **Bivariate Analysis** – Category vs. sales, Gender vs. spending, Age vs. Total Amount
6. **Time Series Analysis** – Monthly trends, day-of-week patterns, seasonal effects
7. **Correlation & Feature Importance** – Heatmap, Random Forest importance scores
8. **Key Findings & Recommendations** – Summary of insights

## Key Findings

- **No data quality issues:** Zero missing values, zero duplicates, all 1,000 Customer IDs are unique
- **Total Amount is deterministic:** Driven entirely by Price per Unit (75.95% importance) and Quantity (24.05%)
- **Product categories differ significantly:**
  - Electronics: highest volume, lowest price points ($30–$50)
  - Clothing: fewest transactions but highest prices ($300–$500)
  - Beauty: mid-range pricing ($25–$50)
- **Temporal patterns:**
  - Saturday is the premium sales day (avg $525.43 per transaction)
  - May is the peak month ($53,150 total sales)
- **Demographics:** Gender-balanced spending; Age (18–64) shows no significant correlation with purchase behavior

## Tech Stack

- **Python 3.x**
- **pandas** – Data manipulation
- **numpy** – Numerical operations
- **matplotlib / seaborn** – Visualizations
- **scikit-learn** – Feature importance (Random Forest)
- **openpyxl** – Excel file reading


## Visualizations

The notebook generates:
- Distribution histograms for all numeric features
- Box plots by Product Category
- Monthly and day-of-week sales trend charts
- Correlation heatmap
- Feature importance bar chart
- Gender and category cross-tabulation plots

## 📗 Project #2 — Machine Learning: Regression Analysis


### Objective
Extend the EDA by building and comparing predictive regression models to estimate **Total Transaction Revenue**, using ensemble learning methods and feature engineering.

### Models Used

| Type | Model |
|---|---|
| Base | Linear Regression |
| Ensemble — Main | ✅ Random Forest Regressor |
| Ensemble — Comparison | XGBoost Regressor |
| Ensemble — Comparison | Gradient Boosting Regressor |

### Feature Engineering

New features derived from the `Date` column:

| Feature | Description |
|---|---|
| `Month` | Month number (1–12) |
| `DayOfWeek` | Day of week (0 = Monday, 6 = Sunday) |
| `IsWeekend` | Binary — 1 if Saturday or Sunday |
| `Quarter` | Quarter of year (Q1–Q4) |
| `Season` | Winter / Spring / Summer / Fall |

**Encoding:** One-Hot Encoding (`pd.get_dummies`) applied to `Gender`, `Product Category`, and `Season` — chosen over Label Encoding to avoid implying a false ordinal ranking between categories.

### Results Summary

| Model | R² Score | MAE ($) | RMSE ($) |
|---|---|---|---|
| **Random Forest ⭐** | **0.9997** | **5.21** | **8.51** |
| XGBoost | 0.9993 | 7.63 | 12.70 |
| Gradient Boosting | 0.9989 | 9.88 | 15.96 |
| Linear Regression | 0.9974 | 14.71 | 23.04 |

> **Random Forest** was the best model — R² = 0.9997, RMSE = $8.51 average prediction error.

### Visualizations Generated
- Correlation heatmap
- Actual vs. Predicted plots (all 4 models)
- Residual plots (all 4 models)
- Feature Importance bar chart (Random Forest)
- Model Comparison R² bar chart

### Key Business Insights

1. **Price per Unit** is the strongest revenue driver — prioritize premium product placement
2. **Quantity** is the second biggest lever — bundle promotions increase average basket size
3. **Electronics** category contributes the highest per-transaction revenue
4. **Q4 seasonality** shows elevated revenue — plan inventory and marketing for holiday peaks
5. **Older customers (40+)** trend toward higher-value purchases — segment for targeted campaigns

---

## 🚀 How to Run

### Google Colab (Recommended for both notebooks)

1. Upload `retail_sales.xlsx` + desired `.ipynb` to Google Drive
2. Open with **Google Colab**
3. For Project #2: Cell 1 auto-installs `xgboost`
4. `Runtime → Run all`

### Local (Jupyter)

```bash
# Clone the repo
git clone https://github.com/your-username/CS667-RetailSales.git
cd CS667-RetailSales

# Install all dependencies
pip install pandas numpy matplotlib seaborn scikit-learn xgboost openpyxl

# Open either notebook
jupyter notebook Project1_EDA/CS667_Project1_EDA.ipynb
jupyter notebook Project2_ML/CS667_Project2_RetailSales.ipynb
```

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| `pandas` | Data manipulation |
| `numpy` | Numerical operations |
| `matplotlib` / `seaborn` | Visualizations |
| `scikit-learn` | ML models, scaling, metrics |
| `xgboost` | XGBoost regressor |
| `openpyxl` | Excel file reading |

> All libraries are pre-installed in Google Colab except `xgboost` — handled automatically in the Project #2 notebook.

---

## 📄 Deliverables

| Project | Deliverable | Status |
|---|---|---|
| #1 | Commented EDA notebook (8 sections) | ✅ |
| #1 | Written observations report (.docx) | ✅ |
| #2 | Commented ML notebook (Colab ready) | ✅ |
| #2 | Performance summary table (R², MAE, MSE, RMSE) | ✅ |
| #2 | All required visualizations | ✅ |
| #2 | Written report (.docx) | ✅ |

---



## License

This project is for academic purposes as part of the CS667 coursework at Pace University.

## Author

**Ananya Saravani Ganni**
- [LinkedIn](https://www.linkedin.com/in/ananyasaravani)
- ananyasaravaniganni@gmail.com


