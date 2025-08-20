- # Retail Sales SQL Dashboard

## Overview
This project demonstrates how SQL can be used to analyze retail sales data and build dashboards with key business insights.  
The dataset includes sales transactions with product, region, and customer details.

## Dataset
Source: [Kaggle - Sample Sales Data](https://www.kaggle.com/datasets/kyanyoga/sample-sales-data)

## Objectives
- Derive KPIs such as:
  - Total revenue and profit
  - Region-wise sales trends
  - Top-performing products/customers
- Use SQL features:
  - Joins
  - Common Table Expressions (CTEs)
  - Window Functions
  - Aggregations

## Tools Used
- MySQL / PostgreSQL
- Power BI (for optional dashboarding)

## Example Queries
```sql
-- Total sales per region
SELECT region, SUM(sales) AS total_sales
FROM sales_data
GROUP BY region
ORDER BY total_sales DESC;

-- Top 5 customers by revenue
SELECT customername, SUM(sales) AS revenue
FROM sales_data
GROUP BY customername
ORDER BY revenue DESC
LIMIT 5;

-- Monthly revenue trend
SELECT DATE_FORMAT(orderdate, '%Y-%m') AS month,
       SUM(sales) AS monthly_revenue
FROM sales_data
GROUP BY month
ORDER BY month;

