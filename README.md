# 🍕 Pizza Sales Analytics Dashboard | End-to-End Power BI Project

## 📌 Project Overview

This project demonstrates an end-to-end Business Intelligence solution using **SQL Server**, **Power Query (M Language)**, **Power BI**, and **DAX** to analyze pizza sales performance.

The objective was to transform raw transactional pizza sales data into an interactive dashboard that provides actionable business insights regarding revenue, customer ordering behavior, product performance, and sales trends.

---

## Dashboard Preview

<img width="1242" height="777" alt="output" src="https://github.com/user-attachments/assets/e972843a-a27d-44ca-80e2-062b61546368" />


---

## Project Workflow

Raw Pizza Sales Dataset
        │
        ▼
SQL Server
(Data Cleaning & SQL Queries)
        │
        ▼
Power Query (M)
(Data Transformation)
        │
        ▼
Data Modeling
(Relationships)
        │
        ▼
DAX Measures
(KPIs & Calculations)
        │
        ▼
Interactive Power BI Dashboard

---

## Technologies Used

- Power BI Desktop
- SQL Server
- SQL
- Power Query (M Language)
- DAX
- Data Modeling
- Microsoft Excel (Dataset)

---

## Dataset

The dataset contains pizza sales transaction records including:

- Order ID
- Order Date
- Pizza Category
- Pizza Size
- Pizza Name
- Quantity
- Unit Price
- Total Price

---

# SQL Server

The raw dataset was imported into SQL Server.

Several SQL queries were written to analyze and validate the data before connecting Power BI.

### Example SQL Queries

### Total Revenue

```sql
SELECT SUM(total_price) AS TotalRevenue
FROM pizza_sales;
```

### Total Orders

```sql
SELECT COUNT(DISTINCT order_id) AS TotalOrders
FROM pizza_sales;
```

### Average Order Value

```sql
SELECT
SUM(total_price)/COUNT(DISTINCT order_id)
AS AvgOrderValue
FROM pizza_sales;
```

### Daily Sales Trend

```sql
SELECT
DATENAME(WEEKDAY, order_date) AS DayName,
SUM(total_price) AS Revenue
FROM pizza_sales
GROUP BY DATENAME(WEEKDAY, order_date);
```

### Monthly Sales

```sql
SELECT
MONTH(order_date) AS Month,
SUM(total_price) AS Revenue
FROM pizza_sales
GROUP BY MONTH(order_date)
ORDER BY Month;
```

---

# Data Transformation (Power Query)

The dataset was cleaned using Power Query (M).

Transformations performed:

- Removed duplicate records
- Changed data types
- Renamed columns
- Removed null values
- Created calculated columns
- Standardized formatting
- Extracted Month
- Extracted Day Name
- Created Date hierarchy

---

# Data Modeling

The Power BI data model includes:

- Sales Table
- Calendar Table
- Relationships
- Date hierarchy

---

# DAX Measures

Some important measures created:

### Total Revenue

```DAX
Total Revenue =
SUM(pizza_sales[total_price])
```

### Total Orders

```DAX
Total Orders =
DISTINCTCOUNT(pizza_sales[order_id])
```

### Total Pizza Sold

```DAX
Total Pizza Sold =
SUM(pizza_sales[quantity])
```

### Average Order Value

```DAX
Avg Order Value =
DIVIDE(
[Total Revenue],
[Total Orders]
)
```

### Average Pizza Per Order

```DAX
Avg Pizza Per Order =
DIVIDE(
[Total Pizza Sold],
[Total Orders]
)
```

---

# Dashboard Features

The dashboard includes:

✅ KPI Cards

- Total Revenue
- Average Order Value
- Total Pizza Sold
- Total Orders
- Average Pizza Per Order

---

### Sales Trend Analysis

- Daily Orders Trend
- Monthly Orders Trend

---

### Category Analysis

- Sales by Pizza Category
- Sales by Pizza Size
- Total Pizza Sold by Category

---

### Business Insights Panel

Key findings:

- Weekend orders are highest.
- June and July recorded maximum orders.
- Classic Pizza category generated the highest sales.
- Large-sized pizzas contributed the highest revenue.

---

# Key Business Insights

### Total Revenue

**208.20K**

### Average Order Value

**22.92**

### Total Pizza Sold

**12K**

### Total Orders

**9K**

### Average Pizza Per Order

**1.32**

---

# Skills Demonstrated

- SQL
- SQL Server
- Power BI
- Power Query
- M Language
- DAX
- Data Cleaning
- Data Modeling
- Dashboard Design
- Business Intelligence
- Data Visualization

---

# Future Improvements

- Forecasting
- Customer Segmentation
- Time Intelligence
- Drill-through Pages
- Row-Level Security
- Power BI Service Deployment
