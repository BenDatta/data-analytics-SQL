# 📊 Data Analytics SQL 

A collection of SQL projects showcasing my **data analytics, database management, and reporting skills**.  
This portfolio demonstrates the ability to transform raw data into actionable insights using advanced SQL techniques.  

---

## 🧰 Key Skills & Tools

| Skill Category         | Tools / Techniques |
|------------------------|------------------|
| SQL Proficiency        | T-SQL, Joins, Subqueries, CTEs, Window Functions |
| Data Analysis          | Aggregation, Filtering, Transformations |
| Database Management    | Schema Design, Optimization, Data Integrity |
| Reporting & Dashboards | KPI Calculation, Data Visualization |
| Version Control        | Git, GitHub |

---

## 🎯 Key Takeaways

- Built **customer segmentation models** (VIP, Regular, New) using behavior and demographics  
- Developed **product performance analyses** with time-series metrics and rolling aggregates  
- Calculated critical KPIs: recency, average order value (AOV), average monthly spend, customer lifespan  
- Created **SQL scripts** demonstrating advanced aggregation, window functions, and conditional logic  
- Produced **recruiter-ready datasets** suitable for BI reporting and dashboards  

---

## 📝 Project Highlights

### 1️⃣ Customer Segmentation & Analysis
**Objective:** Segment customers based on purchase behavior and demographics  
**Techniques:** Aggregation, CASE statements, date functions  
**Key Metrics:**  
- Total orders, total sales, total quantity  
- Customer segment (VIP, Regular, New)  
- Recency, average order value, average monthly spend  

### 2️⃣ Product Performance Analysis
**Objective:** Track product sales performance over time  
**Techniques:** Time-series analysis, window functions, date formatting  
**Key Metrics:**  
- Total sales, total quantity  
- Running total sales  
- Moving average price  

---

## 📈 Example SQL Queries

**Customer Segmentation**
```sql
SELECT
    customer_key,
    customer_name,
    CASE
        WHEN total_sales > 5000 THEN 'VIP'
        WHEN total_sales BETWEEN 1000 AND 5000 THEN 'Regular'
        ELSE 'New'
    END AS customer_segment,
    DATEDIFF(month, last_order_date, GETDATE()) AS recency,
    total_orders,
    total_sales,
    total_quantity,
    total_products,
    lifespan,
    CASE WHEN total_orders = 0 THEN 0 ELSE total_sales / total_orders END AS avg_order_value,
    CASE WHEN lifespan = 0 THEN total_sales ELSE total_sales / lifespan END AS avg_monthly_spend
FROM customer_aggregation;
