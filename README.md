## Samaluko_Capstone_LITAProject
### Sales Performance Analysis 

## Table of Contents
1. [Overview](#overview)
2. [Data Sources](#Data-Sources)
3. [Requirements/Tools_Used](#Requirements/Tools_Used)
4. [Data cleaning and Preparation](#Data-cleaning-and-reparation)
5. [Experimental Data Analysis](#Experimental-Data-Analysis)
6. [Data Analysis](#Data-Analysis)
7. [Data Visualizations](#Data-Visualizations)


### 1. Overview
---
This Data Analysis project aims to generate insight into the sales performance of Sales transactions from various regions and categories. The goal is to deliver an interactive and visually appealing dashboard that helps stakeholders easily understand sales performance across multiple dimensions and also Provides Insight into Revenune and other summaries contained within the data. 

### 2. Data Source
---
The Primary sourcs of Data here is Salesdata.csv and this is an open source that can was given to work with by the Incubators hub, tagged capstone project Dataset.

- Built a Power BI dashboard to visualize sales data, focusing on metrics like total sales, product performance, and regional breakdowns.
- Incorporate findings from Excel and SQL analyses to ensure a comprehensive view of the data.
- Enable users to interact with the dashboard and drill down into specific data points.

### 3. Requirements/ Tools Used 
---
- Microsoft Excel
  1.  For Data cleanig (www.microsoft.com)
     -*Excel File: Use the *Get Data option to connect to the Excel file. Select the relevant tables or sheets that contain summarized sales data, such as total sales, regional breakdowns, and monthly sales
      
- SQL server(For Quering and Analysis)
  2. Connect to Data Sources:
  - *SQL Server Data: Use *Get Data > SQL Server to connect to the SQL Server database and import key tables. Enter your SQL Server credentials and select tables with insights like top-performing products, sales by region, and customer data.

- Power BI Desktop: We used Power BI Desktop application for building the dashboard.
 3. Basic Power BI Knowledge: Familiarity with Power BI visualizations, data modeling, and DAX.
  
-Github for Portfolio Building 

### Data cleaning and Preparation
---
At the initail phase of the Data cleaning and preparations , certains operations were performed
Data Loading and Inspection 
Handling Missing Variables 
Handling Balnk Spaces in the proces of loading the salesdata.csv into the SQL 
Data Cleaning and categorization 


### Experimental Data Analysis
---
EDA involves the exploring of the Data to answer some questions about the Data such as;

-What is the total sales for each product category.
-Whats the sales transactions for each region. 
-How to find the highest-selling product by total sales value.
-How to Calculate total revenue per product.
-How to calculate the monthly sales totals for the current year. 
-How to find top 5 customers by total purchase amount.
-How to calculate the percentage of total sales by each region
-How to identify products with no sales in the last quarter.


### Data Analysis 
---
This is where we include some basic line of code or queries;

SQL
SELECT * FROM SalesDataCsv;
select Product, sum(Total_sales) as Total_sales
from [dbo].[SalesDataCsv]
Group by product

SQL
SELECT TOP 5 Customer_Id,
SUM(Total_sales) AS TotalPurchaseAmount
FROM [dbo].[SalesDataCsv]
GROUP BY Customer_Id
ORDER BY TotalPurchaseAmount DESC;



   - Relationships: Establish relationships between tables based on common fields (e.g., ProductID, CustomerID, Region) if they are in separate tables.
   - Data Transformation: Use Power Query to clean, format, or aggregate data as needed. For example, you might filter data to include only the current year or group data by categories.

4. Data Validation:
   - Review data in Power BI to ensure that imported figures match Excel and SQL outputs.

### 5. Dashboard Components

Create the following visualizations in Power BI for a well-rounded sales dashboard:

#### Sales Overview
1. Total Sales Card:
   - Add a Card visualization to display total sales.
   - Use a DAX measure if needed, such as Total Sales = SUM(SalesAmount).

2. Sales by Month Line Chart:
   - Add a Line Chart to show monthly sales trends over time.
   - Drag Transaction Date to the X-axis and SalesAmount to the Y-axis, and format to display month-over-month performance.

3. Sales by Category Bar Chart:
   - Use a Stacked Bar Chart to display sales by product category.
   - Drag Product Category to the axis and SalesAmount to values to compare sales across different categories.

#### Top-Performing Products
1. Top Products Table:
   - Insert a Table visualization to list the top 10 products by total sales.
   - Use SQL or Excel insights to filter for top products, or use a DAX formula to create a ranking column, such as:
     DAX
     Rank = RANKX(ALL(SalesData), SUM(SalesData[SalesAmount]), , DESC)
     
   - Display fields such as Product Name, Total Sales, and Rank.

2. Product Sales Pie Chart:
   - Add a Pie Chart to show sales distribution by top-performing products.
   - Drag Product Name and Total Sales to the chart fields and filter to show only the top 5 or 10 products.

#### Regional Breakdown
1. Regional Sales Map:
   - Use a Map visualization to display sales by region geographically.
   - Drag Region to the location field and Total Sales to size or color, depending on the preferred visualization.

2. Region Comparison Column Chart:
   - Use a Clustered Column Chart to compare sales by region.
   - Place Region on the X-axis and Total Sales on the Y-axis for a clear comparison.

### 6. Interactivity Features

This allow the users to drill down and filter data:
- Slicers:
  - Add slicers for fields like Product Category, Region, and Time Period to allow users to filter views.
- Drill-Throughs:
  - Enable drill-through functionality to allow users to click on specific data points (e.g., region or product) and view details.
- Tooltips:
  - Customize tooltips to show extra data when hovering over visual elements (e.g., show percentage contribution or customer insights on region breakdowns).
