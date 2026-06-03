# 📊 Global Sales Performance Analysis

## 📌 Project Overview
This project focuses on analyzing historical global retail sales data to uncover key business trends. The analysis is structured around three main pillars: identifying top-performing sales markets, understanding monthly seasonality patterns, and monitoring year-over-year revenue growth.

## 🛠️ Tools Used
- **Database:** MySQL (For data extraction, manipulation, and aggregation)
- **Data Visualization:** [Specify: Excel / Python / Tableau / Power BI]
- **Dataset:** `sales_data_sample.csv`

---

## 🔍 Core Analysis & SQL Queries

### 1. Top Sales Markets Analysis
This analysis identifies which cities or regions generate the highest volume of orders and revenue. These insights help the business optimize logistics, inventory distribution, and targeted marketing strategies in high-potential areas.

```sql
SELECT
     PRODUCTLINE,
     COUNT(*) AS ORDER_COUNT,
     ROUND(SUM(SALES), 2) AS TOTAL_REVENUE
FROM
    portofolio_sample.sales_data_sample
GROUP BY
     PRODUCTLINE
ORDER BY
     TOTAL_REVENUE DESC;
```
### 2. Peak Monthly Sales Analysis (Seasonality)
This query identifies which months experience the highest sales volume throughout the year. Understanding these "peak seasons" allows management to plan promotions, marketing budgets, and stock supply effectively.
```sql
SELECT 
    MONTH_ID, 
    ROUND(SUM(SALES), 2) AS TOTAL_SALES
FROM portofolio_sample.sales_data_sample
GROUP BY MONTH_ID
ORDER BY MONTH_ID;
```
### 3. Year-over-Year Sales Performance
This high-level analysis evaluates the company's total sales performance across different years to track overall growth and determine whether business revenue is scaling up or declining.
```sql
SELECT
     YEAR_ID,
     COUNT(*) AS ORDER_COUNT
FROM portofolio_sample.sales_data_sample
GROUP BY YEAR_ID
ORDER BY ORDER_COUNT DESC;
```
### 4. Top Sales Markets Analysis (By City)
This analysis identifies which cities generate the highest volume of orders and overall revenue. These insights allow the business to understand its primary geographic drivers, optimize logistics, and strategically allocate marketing budgets to high-potential regions.
```sql
Select
     CITY,
     Count(*) AS ORDER_COUNT
FROM portofolio_sample.sales_data_sample
GROUP BY CITY
ORDER BY ORDER_COUNT DESC;
```
### 5. Customer Order Size Analysis
This analysis categorizes transactions based on their deal sizes (Small, Medium, Large). Understanding the distribution of deal sizes helps the business segment its customers effectively, tailor its pricing strategies, and identify whether volume or premium high-ticket orders drive the most revenue.
```sql
SELECT 
    DEALSIZE,
    COUNT(*) AS TOTAL_ORDERS,
    ROUND(SUM(SALES), 2) AS TOTAL_REVENUE
FROM 
    portofolio_sample.sales_data_sample
GROUP BY 
    DEALSIZE
ORDER BY 
    TOTAL_REVENUE DESC;
```
