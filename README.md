# CloudExify Data Science Internship — Project 1
## Sales Data Analysis

### 📊 Overview
This project analyzes retail sales transaction data to uncover revenue trends, top-performing categories/items, and monthly sales patterns. The dataset used is the "Dirty Retail Store Sales" dataset from Kaggle, which contains real-world data quality issues (missing values) requiring a full data cleaning pipeline before analysis.

**Dataset Source:** [Retail Store Sales - Dirty for Data Cleaning](https://www.kaggle.com/datasets/ahmedmohamed2003/retail-store-sales-dirty-for-data-cleaning)

### 🧹 Data Cleaning Process
- Original dataset: 12,575 rows, 11 columns
- **Price/Quantity/Total Spent** (related by the formula `Total = Price × Quantity`): where only one value was missing, it was recalculated using the other two. Where two or more were missing, the row was dropped (604 rows removed) since it could not be reliably reconstructed.
- **Item** column missing values (609 rows) were labeled `"Unknown Item"` rather than dropped, since the rest of the row's data was still usable.
- **Discount Applied** missing values (3,988 rows) were labeled `"Unknown"` rather than guessed as True/False, since a missing discount status is not the same as "no discount."
- Checked for duplicate rows — none found.
- Converted `Transaction Date` to proper datetime format.
- **Final cleaned dataset:** 11,971 rows, 0 missing values.

### 📈 Key Findings
- **Total Revenue:** Rs 1,552,071
- **Average Transaction Value:** Rs 130
- **Median Transaction Value:** Rs 108
- **Best Performing Month:** January 2022 (Rs 52,912)
- **Revenue Split:** Online (Rs 791,401) slightly outperforms In-store (Rs 760,670)
- **Top Category:** Butchers (Rs 208,118), though revenue is fairly evenly distributed across all 8 categories (no single category dominates)

### 📊 Visualizations
See `Sales_Analysis_Charts.docx` for all charts, including:
- Top 10 items by revenue (bar chart)
- Monthly sales trend (line plot)
- Revenue distribution by category (pie chart)
- Revenue by location — Online vs In-store (bar chart)

### 🛠️ Tools Used
- Python (Pandas, Matplotlib)
- Google Colab
- Dataset: Kaggle

### 📁 Files in This Repository
- `Project1_SalesAnalysis.ipynb` — Full analysis notebook
- `report.txt` — Text summary of findings
- `Sales_Analysis_Charts.docx` — Visualization screenshots
- `retail_store_sales.csv` — Dataset used

### 📝 Note on Methodology
This dataset does not include a geographic "Region" column (unlike the project guide's original example). The `Location` column (Online vs In-store) was used in its place, as the closest available equivalent for that part of the analysis.
