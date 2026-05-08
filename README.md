# Customer Behaviour Analysis

An end-to-end data analysis project on retail/e-commerce customer transaction data — covering data cleaning in Python, SQL-based analysis, and a Power BI dashboard.

---

## Project Overview

This project analyzes customer purchasing behavior to help a retail business answer key questions:

- Who are the high-value and loyal customers?
- Do discounts actually drive more spending?
- Which product categories and seasons generate the most revenue?
- How does subscription status affect spending?

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Python (Pandas) | Data cleaning & EDA |
| SQL Server | Business question analysis |
| Power BI | Interactive dashboard |

---

## Dataset

- **Type:** Retail / E-commerce (Structured, Tabular)
- **Level:** Customer Transaction Level
- **Size:** 5,000 customers, 30 unique items
- **Key Columns:** Age, Gender, Category, Purchase Amount, Season, Payment Method, Discount Applied, Previous Purchases, Subscription Status, Frequency of Purchases

---

## Project Workflow

### 1. Data Cleaning (Python)
- Loaded dataset using Pandas
- Fixed category inconsistencies using a mapping dictionary
- Handled missing values with domain logic:
  - `Size` → "Not Applicable" for Electronics/Accessories, mode for Clothing
  - `Review Rating` → filled with product-level mean
  - `Purchase Amount` → filled with mean
  - `Previous Purchases` → filled with 0
- Removed duplicate records (identified by Customer ID)
- Standardized column names (lowercase, underscores)

### 2. Data Export
- Exported cleaned data to SQL Server using `pyodbc` and `sqlalchemy`

### 3. SQL Analysis
Key business questions answered:

1. Which category generates the highest revenue? → **Electronics (486K)**
2. Do discounts increase purchase value? → **Yes — avg spend jumps from 182 to 219**
3. Revenue by gender
4. Customers who used discounts but spent above average
5. Top/bottom 5 products by review rating
6. Standard vs Express shipping comparison
7. Subscribers vs non-subscribers spending
8. Top 5 products by discount usage %
9. Customer segmentation — New, Returning, Loyal
10. Top 3 products within each category
11. Repeat buyers vs subscription likelihood
12. Revenue contribution by age group

### 4. Power BI Dashboard
Two-page interactive dashboard with:
- KPI cards: Total Customers, Unique Items, Avg Rating, Total Spend, Avg Spend
- Revenue by Category, Gender, Age Group, Season
- Shipping type analysis
- Payment method distribution
- Top/Bottom 5 products by rating and revenue
- Top 5 locations by revenue
- Filters: Category, Gender, Discount Applied, Subscription Status

---

## Key Findings

- **Electronics** is the top revenue category (~49% of total)
- Customers aged **51+** contribute the most revenue (40%)
- **Subscribed customers** spend 63% more on average (270 vs 165)
- Discounts lead to **higher average spend** (219 vs 182 without discount)
- **3,085 out of 5,000** customers are classified as Loyal
- **Debit Card** is the most used payment method (25.5%)
- Revenue is nearly equal across seasons — no single dominant season

---

## Repository Structure

```
customer-behaviour-analysis/
│
├── data/
│   └── customer_shopping_behavior.csv
│
├── notebooks/
│   └── eda_cleaning.ipynb
│
├── sql/
│   └── analysis_queries.sql
│
├── dashboard/
│   └── customer_behaviour.pbix
│
└── README.md
```

---

## How to Run

1. Clone the repo
2. Install dependencies:
   ```bash
   pip install pandas pyodbc sqlalchemy
   ```
3. Run the notebook in `/notebooks/` for data cleaning
4. Execute SQL queries from `/sql/` in SQL Server
5. Open the `.pbix` file in Power BI Desktop

---

## Author

**[Kamal Sharma]**
