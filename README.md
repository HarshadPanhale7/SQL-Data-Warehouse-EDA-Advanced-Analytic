# 🧾 SQL Data Warehouse – Exploratory Data Analysis & Advanced Analytics

**Author:** Harshad Panhale
**Date:** 26 July 2026  
**Database:** Microsoft SQL Server  

---

## 📌 Project Overview

This project demonstrates a complete **data warehouse analysis** pipeline, starting from **data exploration** to **advanced business intelligence**. It covers:

- ✅ **Exploratory Data Analysis (EDA)** – understanding the structure and quality of data.
- ✅ **Advanced Analytics** – using window functions, CTEs, subqueries, and complex aggregations.
- ✅ **Reporting** – building reusable views for customer and product performance.

The goal is to extract actionable insights about sales, customers, products, and time trends from a retail dataset.

---

## 🗃️ Dataset Description

The dataset consists of three tables (stored as flat files in the `datasets/` folder):

| Table           | Description                                 |
|-----------------|---------------------------------------------|
| `dim_customers` | Customer details (name, country, birthdate) |
| `dim_products`  | Product details (name, category, cost)      |
| `fact_sales`    | Sales transactions (orders, quantity, price)|

**Relationships:**  
- `fact_sales.customer_key` → `dim_customers.customer_key`  
- `fact_sales.product_key` → `dim_products.product_key`

---

## 🛠️ Tools & Technologies

- **Database:** Microsoft SQL Server  
- **Language:** T‑SQL  
- **Version Control:** Git + GitHub  
- **Data Load:** Flat files imported via SQL Server Import/Export Wizard or `BULK INSERT`

---

## 📂 Project Structure
.
├── datasets/ # Raw CSV files
├── backup/ # Database backup (.bak)
├── scripts/ # All SQL scripts (numbered in order)
│ ├── 01_database_exploration.sql
│ ├── 02_dimensions_exploration.sql
│ ├── ...
│ └── 13_report_products.sql
└── README.md # This file


---

## 🔍 SQL Scripts – What Each Does

| File | Description |
|------|-------------|
| `01_database_exploration.sql` | List all tables and columns in the database. |
| `02_dimensions_exploration.sql` | Explore unique countries, categories, subcategories. |
| `03_date_range_exploration.sql` | Find first/last order date, customer age extremes. |
| `04_measures_exploration.sql` | Compute total sales, items sold, avg price, orders, etc. |
| `05_magnitude_analysis.sql` | Aggregate by country, gender, category, revenue per customer, etc. |
| `06_ranking_analysis.sql` | Top/bottom products and customers using `ROW_NUMBER()`. |
| `07_change_over_time_analysis.sql` | Sales trends by year, month, using `DATETRUNC` and `FORMAT`. |
| `08_cumulative_analysis.sql` | Running totals and moving averages over time. |
| `09_performance_analysis.sql` | Compare product sales vs. average and vs. previous year. |
| `10_data_segmentation.sql` | Segment products by cost range and customers by spending. |
| `11_part_to_whole_analysis.sql` | Percentage contribution of each category to total sales. |
| `12_report_customers.sql` | **Final customer report** with segmentation and KPIs + view. |
| `13_report_products.sql`  | **Final product report** with segmentation and KPIs + view. |

---

## ▶️ How to Run

1. **Restore the database** (if using the `.bak` file) or import the CSV files into your SQL Server.
2. Open SQL Server Management Studio (or your preferred tool).
3. Execute the scripts **in numeric order** (01 → 13) to progressively build the analysis.
4. The final views `selfmade_customer_report` and `selfmade_product_report` are created in steps 12 and 13 – you can query them directly.

> **Note:** Make sure to set the correct database name at the top of each script if needed.

---

## 📊 Key Insights (Summary)

- **Top product category** by revenue: `[e.g., Electronics]` – see script 11.
- **Highest revenue customer** – script 06.
- **Seasonal peaks** – script 07 shows highest sales in December.
- **Customer segmentation** – approximately X% VIP, Y% Regular, Z% New (script 10).
- **Product performance** – high‑performers (>50k sales) dominate 60% of revenue (script 13).


---

## 🚀 Future Improvements

- Add a dashboard (Power BI / Tableau) using the views.
- Automate data loading with an ETL pipeline.
- Incorporate more dimensions (e.g., geography, time).
