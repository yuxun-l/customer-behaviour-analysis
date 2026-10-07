# Customer Shopping Behaviour Analysis

An end-to-end data analytics project that uses **Python, PostgreSQL, and Power BI** to analyse 3,900 retail purchases and turn them into clear business recommendations.

---

## Overview

A retail company wants to understand how customers shop so it can improve sales, satisfaction, and loyalty. This project explores spending patterns, customer segments, product preferences, and subscription behaviour to answer one question:

> *How can the company use shopping data to improve customer engagement and optimise marketing and product strategy?*

## Dataset

- **Size:** 3,900 rows and 18 columns (one row per customer purchase)
- **Contents:** demographics, product details, transaction details, and behavioural data such as reviews, subscriptions, and discounts
- **Data quality:** 37 missing values in `Review Rating`, no duplicate rows
- **Source:** [customer_shopping_behavior.csv](https://github.com/amlanmohanty1/customer-trends-data-analysis-SQL-Python-PowerBI/blob/main/customer_shopping_behavior.csv), provided by Amlan Mohanty ([@amlanmohanty1](https://github.com/amlanmohanty1)) in the YouTube tutorial [COMPLETE Data Analytics Portfolio Project in 6 EASY Steps | Python + SQL + Power BI](https://www.youtube.com/watch?v=5PrZvPeUw60)
- **File in this repo:** `customer_shopping_behavior.csv`

| Group | Columns |
|-------|---------|
| Demographics | Customer ID, Age, Gender, Location |
| Product | Item Purchased, Category, Size, Color, Season |
| Transaction | Purchase Amount (USD), Shipping Type, Payment Method |
| Behaviour | Review Rating, Subscription Status, Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases |

## Tools

| Tool | Used for |
|------|----------|
| **Python** (pandas) | Data cleaning, EDA, feature engineering |
| **PostgreSQL** | Business analysis with SQL queries |
| **Power BI** | Interactive dashboard |
| **Git & GitHub** | Version control |

## Steps

1. **Explore (Python):** inspected structure and summary statistics with `df.info()` and `df.describe()`.
2. **Clean (Python):**
   - Filled missing review ratings with the median rating of each product category
   - Standardised column names to lowercase snake_case
   - Removed the redundant `promo_code_used` column (identical to `discount_applied`)
3. **Engineer features (Python):** created `age_group` and `purchase_frequency_days`.
4. **Load (Python to PostgreSQL):** loaded the cleaned data into a PostgreSQL table.
5. **Analyse (SQL):** answered 10 business questions, including revenue by gender and age group, subscriber vs. non-subscriber spend, discount-dependent products, customer segmentation (New, Returning, Loyal), and top products per category using window functions.
6. **Visualise (Power BI):** built an interactive dashboard with filters and KPIs.
7. **Report:** summarised the findings and recommendations in a written report.

## Dashboard

The Power BI dashboard includes:

- **KPIs:** number of customers, average purchase amount, average review rating
- **Charts:** subscription share, revenue and sales by category, revenue and sales by age group
- **Filters:** subscription status, gender, category, and shipping type

## Results

- **3,900 customers** with an average purchase of **$59.76** and an average rating of **3.75**
- **Clothing and Accessories** generate roughly three quarters of revenue
- **Young Adults** are the top revenue group ($62,143), followed by Middle-aged ($59,197)
- Only **27% of customers subscribe**, and subscribers spend about the same as non-subscribers ($59.49 vs. $59.87)
- **Express shipping** orders average more ($60.48) than Standard ($58.46)
- **3,116 customers** are classed as Loyal, 701 as Returning, and 83 as New
- Highest-rated products: Gloves (3.86), Sandals (3.84), Boots (3.82)

**Recommendations**
1. Launch a loyalty and subscription conversion campaign aimed at the 73% of non-subscribers, with perks beyond price.
2. Invest in Clothing and Accessories through stock depth, featured placement, and bundles.
3. Fix issues in low-rated best sellers and promote highly rated items.

## How to Run

**Requirements:** Python 3.9+, PostgreSQL, Power BI Desktop

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/customer-shopping-behaviour-analysis.git
cd customer-shopping-behaviour-analysis

# 2. Install dependencies
pip install pandas sqlalchemy psycopg2-binary jupyter
```

1. Open the notebook in `python/`, update the PostgreSQL connection details, and run all cells to clean the data and load it into the database.
2. Run the queries in `sql/` against the loaded table.
3. Open the `.pbix` file in `powerbi/` with Power BI Desktop and refresh the data source.
4. Read the full write-up in `reports/`.

## Repository Structure

```
├── data/        # Raw dataset
├── python/      # Cleaning, EDA, and database load notebook
├── sql/         # PostgreSQL analysis queries
├── powerbi/     # Power BI dashboard (.pbix)
├── reports/     # Project report
├── images/      # Dashboard screenshots
└── README.md
```

## Author

**Your Name** · [LinkedIn](https://linkedin.com/in/your-profile) · [GitHub](https://github.com/your-username) · your.email@example.com
