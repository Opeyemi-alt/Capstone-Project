# Capstone-Project
This is where My Capstone projects are documented  while learning Data Analysis with the Incubator Hub

### Project Title
---
Sales Performance Analysis for Retail Store

[Project Objective](#project-Objective)

[Project Scope](#project-scope)

[Key Performance Indicators (KPIs)](#key-ierformance-Indicators-(KPIs))

[Data Sources](data-sources)

[Tools and Technologies](#tools-and-technologies)

[Data Cleaning and Preparations](#data-cleaning-and-preparations)

[Data Analysis](#data-analysis)

[Data Visualization](#data-visualization)

[Project Status](#project-status)


### Project Objective
---
To design and develop a comprehensive sales performance analysis dashboard using Excel, SQL, and Power BI, providing actionable insights into top-selling products, regional performance, and monthly sales trends for a retail store.


### Project Scope:
---
1. Data Collection: Extract sales data from the retail store's database using SQL.

2. Data Analysis: Analyze sales data using Excel to identify:

    - Top-selling products
    - Regional sales performance
    - Monthly sales trends
    - Seasonal fluctuations
    - Product category sales

3. Data Visualization: Create interactive dashboards using Power BI to visualize sales performance.


### Key Performance Indicators (KPIs)
---
1. Sales Revenue
2. Sales Growth Rate
3. Top-Selling Products
4. Regional Sales Performance
5. Monthly Sales Trends
6. Product Category Sales

### Data Sources:
---
1. Sales Database (Excel)

### Tools and Technologies:
---
1. Excel (Data Analysis, Pivot Tables, Charts)
2. SQL (Data Extraction, Querying)
3. Power BI (Data Visualization, Dashboard Creation)
4. Microsoft Azure (Data Storage, Integration)

### Data Cleaning and Preparations
---
 The following actions were performed at the inital Phase;
 1) Data loading and Inspection
 2) Handling missing variables
 3) Data cleaning and formatting


###  Project Deliverables:
---
1. Sales Performance Dashboard (Power BI)
  
2. Sales Analysis Report (Excel)
   
3. SQL Queries for Data Extraction
   

### Timeline:
---
1. Data Collection and Analysis (available)
2. Dashboard Creation (few days)
3. Testing and Validation (few days)
5. Project Completion (ongoing)

### Assumptions and Dependencies:
---
1. Access to retail store's database and IT infrastructure.
2. Availability of necessary tools and software.


### Project Benefits:
---
1. Data-driven sales strategies.
2. Improved product inventory management.
3. Enhanced regional sales performance.
4. Increased customer retention.


### Project Risks:
---
1. Data quality issues.
2. Technical difficulties with tool integration.
3. Stakeholder communication challenges.

### Dashboard Components:
---
1. Top-Selling Products by Category
2. Regional Sales Performance Map
3. Monthly Sales Trends Line Chart
4. Product Category Sales Bar Chart
5. Customer Retention Rate Gauge
6. Average Transaction Value (ATV) Metric

### Target Audience:
---
1. Retail Store Management
2. Sales and Marketing Teams
3. Product Managers
4. Operations Manager

### Security and Access:
---
1. Role-based access control
2. Data encryption
3. Secure authentication

### Data Analysis
---
This is where Basic lines of codes or queries are included during my analysis
```Excel
Average sales
=AVERAGEIF(C2:C50001,C2,H2:H50001)

Total Revenue by region
=SUMIFS(H2:H50001,D2:D50001,D2)

```
```SQL
----------CAPSTONE PROJECT-------
SELECT*FROM[dbo].[capstone new]

----TOTAL SALES FOR EACH PRODUCT CATEGORY-------

SELECT PRODUCT,SUM(Total_Sales)as TotalSales 
From [dbo].[capstone new]
GROUP BY PRODUCT
order by TotalSales DESC;

------NUMBER OF SALES OF TRANSACTION IN EACH REGION----
SELECT Region,COUNT(OrderId) AS NumberOfSalesTransactions
FROM [dbo].[capstone new]
GROUP BY Region
ORDER BY NumberOfSalesTransactions DESC;

-----HIGHEST SELLING PRODUCT BY TOTAL SALES-----

SELECT TOP 1 PRODUCT,SUM(Total_Sales)as TotalSales 
From [dbo].[capstone new]
GROUP BY PRODUCT
order by TotalSales DESC;

-----TOTAL REVENUE PER PRODUCT----

SELECT PRODUCT,SUM(Total_Sales)as TotalRevenue 
From [dbo].[capstone new]
GROUP BY PRODUCT
order by TotalRevenue DESC;

----Total Monthly Sales For Current Year-----

SELECT MONTH(OrderDate)as SalesMonth,
SUM(Total_Sales)as TotalMonthlySales 
From [dbo].[capstone new]
WHERE YEAR(OrderDate)=YEAR(OrderDate)
GROUP BY MONTH(OrderDate)
order by SalesMonth DESC;


-----Top 5 Customers by total purchase amount-----

SELECT TOP 5 Customer_Id,SUM(Total_Sales)as TotalPurchaseAmount 
From [dbo].[capstone new]
GROUP BY Customer_Id
order by TotalPurchaseAmount DESC;


------Percentage of total sales contributed by each Region---

SELECT
Region,SUM(Total_Sales)  RegionalSales,
CAST((SUM(Total_Sales)*1.0/(SELECT SUM(Total_Sales)FROM [dbo].[capstone new])) * 100 as DECIMAL(10,2)) PercentageOfTotalSales
FROM [dbo].[capstone new]
GROUP BY Region
ORDER BY RegionalSales DESC;

----Products With no Sales in the last quater----

SELECT Product,OrderID 
From Product
WHERE OrderID NOT IN(
SELECT OrderID FROM[dbo].[capstone new]
WHERE OrderDate>=DATEADD(QUARTER,-1,GETDATE()));
````

### Data Visualization
<img width="713" alt="Total sales capstone" src="https://github.com/user-attachments/assets/7f56bd85-af8c-401d-85ec-0d9a781113dd">

<img width="891" alt="Tables in sales data capstone" src="https://github.com/user-attachments/assets/68bf82f6-9e60-41ae-b499-6c8144e6e753">

![WhatsApp Image 2024-11-05 at 12 46 02_dfa7c416](https://github.com/user-attachments/assets/2484852f-f16f-4ab4-ac3a-3bded29a80c7)



![WhatsApp Image 2024-11-05 at 12 53 11_85a2ac37](https://github.com/user-attachments/assets/d27afb0b-39d6-4493-8533-b4313a2e5553)

### Project Status:
   In Progress




