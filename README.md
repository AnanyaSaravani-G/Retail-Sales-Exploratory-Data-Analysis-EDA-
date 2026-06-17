# Retail Sales Exploratory Data Analysis (EDA)


## Overview

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
├── EDA_Observations_Report.docx      # Detailed findings & conclusions
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

## How to Run

```bash
# Clone the repo
git clone https://github.com/<your-username>/retail-sales-eda.git
cd retail-sales-eda

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl

# Open the notebook
jupyter notebook CS667_Project1_EDA.ipynb
```

Or upload `CS667_Project1_EDA.ipynb` and `retail_sales.xlsx` to [Google Colab](https://colab.research.google.com/) and run all cells.

## Sample Visualizations

The notebook generates:
- Distribution histograms for all numeric features
- Box plots by Product Category
- Monthly and day-of-week sales trend charts
- Correlation heatmap
- Feature importance bar chart
- Gender and category cross-tabulation plots

## License

This project is for academic purposes as part of the CS667 coursework at Pace University.

## Author

**Ananya Saravani Ganni**
- [LinkedIn](https://www.linkedin.com/in/ananyasaravani)
- ananyasaravaniganni@gmail.com


