Sales Data Analysis
Overview
The goal of the Sales Data Analysis is to provide insights into product performance, regional sales distribution, and monthly sales trends. We utilized Excel for initial exploration, SQL for structured analysis, and Power BI for data visualization.

Steps
1. Excel Analysis
Objective: Gained a preliminary understanding of sales data using pivot tables and Excel formulas.

Data Summary:
- Imported data with key fields such as Product, Region, Sales Amount, and Date of Transaction.
- Created pivot tables to aggregate and view data by product, region, and month.

<img width="580" alt="Sales Dashboard" src="https://github.com/user-attachments/assets/651c4b9d-3d19-4430-b3f5-34e2e04d5d26">

![Sales Pivot A](https://github.com/user-attachments/assets/cbf8726f-cc54-46c9-b74f-56c60a629597)

![Sales Pivot B](https://github.com/user-attachments/assets/28e6cb38-3c46-4d27-8aa8-c545f4c1514d)

Key Metrics Calculated:
- Total Sales by Product: Generated a pivot table to identify top-selling products.
- Revenue by Region: Calculated the total sales per region.
- Monthly Sales Trends: Pivoted data by month to observe seasonal patterns.

  -------
2. SQL Analysis
Objective: Write SQL queries to extract deeper insights and validate findings from Excel.

Key SQL Queries:
Total Sales for Each Product Category:
sql
Copy code
SELECT ProductCategory, SUM(SalesAmount) AS TotalSales
FROM Sales
GROUP BY ProductCategory;
Number of Sales Transactions per Region:
sql
Copy code
SELECT Region, COUNT(TransactionID) AS TransactionCount
FROM Sales
GROUP BY Region;
Top 5 Customers by Total Purchase Amount:
sql
Copy code
SELECT CustomerID, SUM(SalesAmount) AS TotalSpent
FROM Sales
GROUP BY CustomerID
ORDER BY TotalSpent DESC
LIMIT 5;
Monthly Sales for Current Year:
sql
Copy code
SELECT MONTH(TransactionDate) AS Month, SUM(SalesAmount) AS MonthlySales
FROM Sales
WHERE YEAR(TransactionDate) = YEAR(GETDATE())
GROUP BY MONTH(TransactionDate);
3. Power BI Dashboard
Objective: Visualize sales data insights in an interactive Power BI dashboard.

Dashboard Elements:
Total Sales by Product Category (Donut Chart).
Monthly Sales Trends (Line Chart).
Top-Selling Products and Top 5 Customers (Bar Charts).
Regional Sales Performance (Map visual showing total revenue by region).
Conclusion for Sales Data
The Sales Data Analysis reveals patterns in product performance, regional differences in sales, and seasonal trends. The insights guide inventory management, marketing strategies, and resource allocation to focus on top-performing products and regions.



