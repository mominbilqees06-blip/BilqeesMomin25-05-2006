# BilqeesMomin25-05-2006
The primary objective of this task is to analyze how sales patterns evolve over time by examining monthly revenue and order volume.The dataset used in this project, named online_sales
# 📊 Sales Trend Analysis Using SQL Aggregations
This project performs monthly sales trend analysis using SQL aggregation functions on the `online_sales` dataset. The goal is to calculate **monthly revenue** and **order volume**, and understand patterns over time.
📁 Dataset Description
**Table Name:** `online_sales`  
**Columns:**
- `order_id` – Unique ID for each order  
- `order_date` – Date of the order  
- `amount` – Revenue amount of each order  
- `product_id` – ID of the product sold  

🛠 Tools Used
- **PostgreSQL / MySQL / SQLite** (SQL Engine)
- **Excel** (Dataset creation & preprocessing)
- **PowerPoint** (Visualization & presentation)
- **Matplotlib** (Charts for PPT – optional)

📌 Key SQL Concepts Used
- `GROUP BY` (year, month)
- `SUM(amount)` to calculate monthly revenue
- `COUNT(DISTINCT order_id)` to calculate total monthly orders
- `EXTRACT(YEAR/MONTH)` to separate date components
- `ORDER BY` to sort results chronologically

🧠 Objective
Analyze **monthly revenue trends** and **monthly order volume** to understand sales patterns and support business decision-making.

📝 SQL Query (PostgreSQL)
```sql
SELECT
    EXTRACT(YEAR FROM order_date) AS year,
    EXTRACT(MONTH FROM order_date) AS month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS total_orders
FROM online_sales
GROUP BY year, month
ORDER BY year, month;
