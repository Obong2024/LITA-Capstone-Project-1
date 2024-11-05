# LITA-Capstone-Project-1-Documentation

I am a data analyst in training at LADIES IN TECH AFRICA INCUBATOR HUB, where I am honing my skills in data manipulation, analysis, and visualization. This comprehensive experience is enhancing my understanding of data-driven decision-making, empowering me to uncover valuable patterns and insights through hands-on, project-based learning

### Title of Project:  SALES PERFORMANCE ANALYSIS FOR A RETAIL STORE

[Project Overview](#project-overview)

[Project Objectives](#project-objectives)

[Data Sources](#data-sources)

[Key Performance Metrics](#key-performance-metrics)

[Tools Used](#tools-used)

[Data Analysis](#data-analysis)

[Data Visualization](#data-visualization)

### Project Overview 
------
The project focuses on exploring, collecting, and analyzing the sales performance of a retail store to reveal key insights, such as best-selling products, regional performance, and monthly sales trends. Excel formulas will be used to calculate metrics like average sales per product and total revenue by region. The ultimate goal is to create an interactive Power BI dashboard that showcases these findings


### Project Objectives
------

The objectives of this project were defined to accomplish the following analytical goals:

#### Instructions:
1.

### Excel:

- Perform an initial exploration of the sales data. Use pivot tables to summarize total sales by product, region, and month.

- Use Excel formulas to calculate metrics such as average sales per product and total revenue by region.

- Create any other interesting report

### Data Sources
------

The data sources consist of the following key elements:
1.	OrderID:This is a unique identifier for each order placed. It helps in tracking and differentiating orders in a system.
2.	CustomerID:A unique identifier for each customer. This links orders to specific customers and helps in customer management.
3.	Product:The name or identifier of the product being ordered. This represents what the customer is purchasing.
4.	Region: Refers to the geographical location where the order was placed or where the product is to be delivered. This helps in understanding the distribution and sales patterns across different regions.
5.	OrderDate: The date when the order was placed. This helps in tracking the timeline of orders and analyzing trends over time.
6.	Quantity: The number of units of the product ordered. It reflects the volume of items in a particular order.
7.	UnitPrice: The price per unit of the product. This helps in calculating the total value of the order (by multiplying with the quantity).

### Key Performance Metrics
------

(i) Revenue: This is the total sales income generated from various regions and stores.

(ii) Total Sales: This refers to total quantity of units of products sold at a specific period across different regions and stores.

(iii) Products: This is simply the classification of products to analyze customer purchasing behavior.

### Used Tools
---------


### Microsoft Excel: [download here](https://www.microsoft.com/en-ng/)

- Pivot Tables: Used for summarizing data and deriving insights related to revenue, units sold, and transaction categories.
- Formulas and Functions: Essential for calculating performance metrics, calculations, data analysis, and to automate tasks.
- Data Visualizations (Charts and Graphs): Employed to produce visual representations of trends, comparisons, and critical insights.

### Exploratory Data Analysis (EDA):
Exploratory Data Analysis (EDA) involves examining the data to address various questions, such as:
- What is the average sales per product and total revenue by region?
- Top-selling products, regional performance, and monthly sales trends?
- Which Region or Product has the lowest number of units sold?


### Data Aalysis
-------

- Activated the pivot table command
- Created a chart to visualize the sales

2.
### SQL:

### Used Tools
---------


### My SQL: [download here](https://www.my-sql-enterprise.com/en-ng/)

Here I am required to Write queries to extract key insights based on the following questions.

- retrieve the total sales for each product category.

- find the number of sales transactions in each region.

- find the highest-selling product by total sales value.

- calculate total revenue per product.

- calculate monthly sales totals for the current year.

- find the top 5 customers by total purchase amount.

- calculate the percentage of total sales contributed by each region.

- identify products with no sales in the last quarter.

### Query 1. Write a query to retrieve the total sales for each product category.
  
```SQL
  SELECT Product, SUM(Quantity) AS TotalSales

   FROM SalesData$

   GROUP BY Product;
  ```

### Query 2. Write a query to find the number of sales transactions in each region.

```
SELECT Region, COUNT(OrderID) AS TotalTransactions

   FROM SalesData$

   GROUP BY Region;
 ```

### Query 3. Write a query to Find the highest-selling product by total sales value:

```
   SELECT TOP 1 Product, SUM(Quantity * UnitPrice) AS TotalSalesValue

    FROM SalesData$

    GROUP BY Product

   ORDER BY TotalSalesValue DESC;
```

### Query 4. Write a query to Calculate total revenue per product: 

```
   SELECT Product, SUM(Quantity * UnitPrice) AS TotalRevenue

   FROM SalesData$

   GROUP BY Product;
```

### Query 5. Write a query to Calculate monthly sales totals for the current year:

```
   SELECT MONTH(OrderDate) AS Month, SUM(Quantity * UnitPrice) AS MonthlySalesTotal

   FROM SalesData$

   WHERE YEAR(OrderDate) = YEAR(GETDATE())

   GROUP BY MONTH(OrderDate)

   ORDER BY Month;
```

### Query 6. Write a query to Find the top 5 customers by total purchase amount:

```
   SELECT TOP 5 [Customer Id], SUM(Quantity * UnitPrice) AS TotalPurchaseAmount

   FROM SalesData$

   GROUP BY [Customer Id]

   ORDER BY TotalPurchaseAmount DESC;
```

### Query 7. Write a query to Calculate the percentage of total sales contributed by each region:

```
   WITH RegionSales AS (

       SELECT Region, SUM(Quantity * UnitPrice) AS RegionalSales

       FROM SalesData$

       GROUP BY Region

   )

   SELECT 

       Region,

       RegionalSales,

       CAST(RegionalSales * 100.0 / SUM(RegionalSales) OVER () AS DECIMAL(5, 2)) AS SalesPercentage

   FROM RegionSales;
   ```

### Query 8. Write a queryy to Identify products with no sales in the last quarter:

```
   SELECT DISTINCT Product

   FROM SalesData$

   WHERE Product NOT IN (

       SELECT Product

       FROM SalesData$

       WHERE OrderDate >= DATEADD(quarter, -1, GETDATE())

   );
```




### DATA VISUALIZATION
---------
### PIVOT TABLE AND CHARTS SHOWING;

- Sales by Products

- Sales by Region

- Sales per Month
   



 ![SALES BY PRODUCT](https://github.com/user-attachments/assets/037d622a-edf1-4ebf-8ac9-387dc15b7512)







![SALES BY REGION](https://github.com/user-attachments/assets/66f0a5a9-6ea0-4c9b-97e9-e92882bcbfc4)










![SALES PER MONTH](https://github.com/user-attachments/assets/ddad8ed8-39ed-42ed-897a-f112bb0b13fa)









![Chart_Sales by Product](https://github.com/user-attachments/assets/7f5d3e66-2ef1-48a3-9111-483adf223450)










![Chart_Sales b Region](https://github.com/user-attachments/assets/871d9b8b-5c7f-4a38-a12f-fa479eea7708)









