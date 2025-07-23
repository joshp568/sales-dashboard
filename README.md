# 📊 Superstore Sales & Profit Dashboard (Power BI + SQL)

An interactive business dashboard built using Power BI and SQL that analyzes global sales and profit performance across regions, categories, and customer segments.

---

## 🚀 Live Project  
👉 [🔗 View Dashboard on GitHub Pages](https://joshp568.github.io/sales-dashboard/)  
📄 [Download PDF Version](https://joshp568.github.io/sales-dashboard/SalesPerformance_Dashboard_final.pdf)  
📁 [Download Power BI File (.pbix)](https://github.com/joshp568/sales-dashboard/raw/main/SalesPerformance_Dashboard.pbix)

---

## 🧰 Tools & Technologies

- **SQL** – Data transformation, aggregation, and filtering  
- **Power BI** – Visual dashboard, insights, slicers  
- **Excel** – Raw data source (orders, customers, categories)

---

## 📈 Key Business Insights

- **$12.6M Total Sales** | **$1.5M Total Profit**
- **26.3% YoY Sales Growth** → $15M+ projected next year
- **Top Performing Region:** Central  
  - $2.8M Sales | $311K Profit | 11.03% Margin  
- **Low Performing Region:** Southeast Asia (2% margin)
- **Top Category:** Technology  
  - $4.7M Sales | $660K Profit
- **Top Segment:** Consumer  
  - 51% of total sales & profit

---

## 🧠 Business Recommendations

- Replicate Central region's tactics across weaker markets  
- Focus Q4 ads and upselling on Technology category  
- Launch loyalty programs for high-value Consumer segment  

---

## 💾 SQL Queries Used

Below are some of the key SQL queries used for preparing data before loading into Power BI:

### 1. Total Sales and Profit by Year
```sql
SELECT 
    YEAR(OrderDate) AS OrderYear,
    SUM(Sales) AS TotalSales,
    SUM(Profit) AS TotalProfit
FROM Orders
GROUP BY YEAR(OrderDate)
ORDER BY OrderYear;

### 2. Total Sales by Region

```sql
SELECT 
    Region,
    SUM(Sales) AS TotalSales
FROM Orders
GROUP BY Region
ORDER BY TotalSales DESC;

### 3. Segment-Wise Profit and Sales

```sql
SELECT 
    Segment,
    SUM(Sales) AS TotalSales,
    SUM(Profit) AS TotalProfit
FROM Orders
GROUP BY Segment;

### 4. Top 5 Countries by Sales

```sql
SELECT 
    Country,
    SUM(Sales) AS TotalSales
FROM Orders
GROUP BY Country
ORDER BY TotalSales DESC
LIMIT 5;

### 5. Profit Margin by Year

```sql
SELECT 
    YEAR(OrderDate) AS OrderYear,
    SUM(Profit) / SUM(Sales) * 100 AS ProfitMargin
FROM Orders
GROUP BY YEAR(OrderDate);

📐 Sample DAX Measure (Power BI)
DAX

Sales Growth YoY = 
VAR PrevYear = CALCULATE(SUM(Orders[Sales]), DATEADD(Orders[OrderDate], -1, YEAR))
RETURN DIVIDE(SUM(Orders[Sales]) - PrevYear, PrevYear, 0)

📌 Project Goals
Transform raw transactional data into actionable insights

Practice data storytelling using KPI visuals

Showcase SQL-Power BI integration for analytics jobs

📬 Contact
If you liked this project or have feedback, feel free to connect:
📧 LinkedIn Profile

© 2025 Joshua – Built using Power BI and SQL
