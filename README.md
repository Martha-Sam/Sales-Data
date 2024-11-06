# Sales Data Analysis

### Overview
The goal of the Sales Data Analysis is to provide insights into product performance, regional sales distribution, and monthly sales trends. 
I utilized Excel for initial exploration and pivotting, SQL for structured analysis, and Power BI for data visualization.

#### Steps
1. Excel Analysis
Objective: Gained a preliminary understanding of sales data using pivot tables and Excel formulas.

Data Summary:
- Imported data with key fields such as Product, Region, Sales Amount, and Date of Transaction.
- Created pivot tables to aggregate and view data by product, region, and month.
  
  Key Metrics Calculated:
- Total Sales by Product: Generated a pivot table to identify top-selling products.
- Revenue by Region: Calculated the total sales per region.
- Monthly Sales Trends: Pivoted data by month to observe seasonal patterns.
- Top & Bottom Selling Product

![Sales Pivot A](https://github.com/user-attachments/assets/cbf8726f-cc54-46c9-b74f-56c60a629597)

![Sales Pivot B](https://github.com/user-attachments/assets/28e6cb38-3c46-4d27-8aa8-c545f4c1514d)

- Charts: To further validate the insights gotten from Pivot
  
![Sales Chart A](https://github.com/user-attachments/assets/482cd734-c4bf-4ee5-bc65-05bf334442f4)  
![Sales Chart B](https://github.com/user-attachments/assets/339bf2ab-61b5-4a40-84bb-237ce7232dcb)

  -------
2. SQL Analysis
Objective: to extract deeper insights and validate findings from Excel.

Key SQL Queries:
Total Sales for Each Product Category:
```sql
SELECT ProductCategory, SUM(SalesAmount) AS TotalSales
FROM Sales
GROUP BY ProductCategory;
Number of Sales Transactions per Region:
```

```sql
Copy code
SELECT Region, COUNT(TransactionID) AS TransactionCount
FROM Sales
GROUP BY Region;
Top 5 Customers by Total Purchase Amount:
```

```sql
SELECT CustomerID, SUM(SalesAmount) AS TotalSpent
FROM Sales
GROUP BY CustomerID
ORDER BY TotalSpent DESC
LIMIT 5;
Monthly Sales for Current Year:
```

```sql
SELECT MONTH(TransactionDate) AS Month, SUM(SalesAmount) AS MonthlySales
FROM Sales
WHERE YEAR(TransactionDate) = YEAR(GETDATE())
GROUP BY MONTH(TransactionDate);
```

![Query 1](https://github.com/user-attachments/assets/6cb58184-36cc-474c-94ac-f6b7a7585edc)
![Query 2](https://github.com/user-attachments/assets/a8b866d8-9112-4f71-9fe0-d3a6bff4c219)
![Query 3](https://github.com/user-attachments/assets/800786a0-7e5c-4976-b20c-d8ebc72f0d9c)
![Query 4](https://github.com/user-attachments/assets/1ecbc29d-6294-4920-9490-72a75232031e)

![Query 5](https://github.com/user-attachments/assets/ef175f45-d85d-4c96-aba6-872e47267e5f)
![Query 6](https://github.com/user-attachments/assets/41f02b33-136c-4e80-ba8b-279923fa44a9)
![Query 7](https://github.com/user-attachments/assets/27d75c00-530c-482d-91a3-b0c1800a3a63)
![Query 8](https://github.com/user-attachments/assets/666c4724-a05d-41bf-850e-b40603fd0830)


3. Power BI Dashboard
Objective: Visualize sales data insights in an interactive Power BI dashboard.

Dashboard Elements:
- Total Sales by Product Category (Donut Chart).
- Monthly Sales Trends (Line Chart).
- Top-Selling Products and Top 5 Customers (Bar Charts).
- Regional Sales Performance (Map visual showing total revenue by region).

<img width="580" alt="Screenshot 2024-11-05 203913" src="https://github.com/user-attachments/assets/cf1f68d0-1f3c-45ad-ab90-bed8fcdb56d7">

Conclusion for Sales Data
The Sales Data Analysis reveals patterns in product performance, regional differences in sales, and seasonal trends. The insights guide inventory management, marketing strategies, and resource allocation to focus on top-performing products and regions.



