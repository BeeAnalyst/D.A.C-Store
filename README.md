# D.A.C Datastore: Power BI Sales Analysis

A Power BI dashboard for a fictional offline retail store, built from a business requirements brief. It covers product performance, sales trends, promotions and sales by city.

## Business Context
The store sells across 8 categories: Electronics, Footwear, Clothing, Home Appliances, Accessories, Kitchenware, Bags and Personal Care. The brief asked for:

1. Top/Bottom 5 products by sales, profit and quantity sold
2. Sales trends over time
3. Relationship between sales and profit
4. Comparison of any two user-selected periods
5. Average discount by discount category
6. Total number of orders
7. Order-level detail filterable by product, date, customer and promotion
8. Sales by city

## Data
Four tables: a transactions fact table (3,510 rows, Jan 2020 to Jan 2024) and three dimensions, Customers (50, across 16 cities), Products (30) and Promotions (5). All prices are in INR.

## Data Preparation (Power Query)
I used Power Query to prepare the dataset before building the dashboard.
The process included:
-Importing the Excel dataset into Power BI.
-Reviewing the structure of each table.
-Applying appropriate data types to text, numeric, and date columns.
**Dim Promotion**
- Promoted the first row to column headers (it had been loaded as data)
- Created a `Percentage` column from the price-reduction text (e.g. "20% off" becomes 20), then set the data types
**Fact Table**
- Calculated Price Per Unit, Total Sales, Discount Percentage, Discount, Net Sales, Profit and Order ID
- Profit is calculated as 10% of Net Sales (assumption, as the source data has no cost field)
-Preparing the tables for data modelling and analysis.

## Dashboard Pages
1. **Overview**: order count, sales trend, sales vs profit, average discount by product, sales by city
2. **Product Performance**: top and bottom 5 by sales, profit and quantity
3. **Period Comparison**: two date selectors to compare units, profit and sales

## Key Findings
- **Electronics carries the business.** 5 of the 30 products generate about 73% of sales. The top five by sales are iPhone 14, Sony Bravia TV, HP Pavilion, MacBook Air and Galaxy S21.
- **Sales were up in 2023, but not a growth story.** Annual sales were roughly 33.2M (2020), 31.2M (2021), 29.7M (2022) and 35.3M (2023). Within 2023, Q3 was the peak (about 10.8M against 7.5M in Q2). One year of quarterly data isn't enough to call it seasonal.
- **Promotions are used on a minority of orders.** About a quarter of 2023 orders carried a promotion, and discounts came to roughly 8.5% of gross sales. The 20% Summer Sale was the most used by a wide margin.
- **Sales are concentrated in central and northern cities.** Bhopal, Indore and Kanpur lead, with Mumbai and Pune behind them.

## Limitations
- Profit was assumed 10% margin, so profit insights mirror sales insights.
- Customer and product data is synthetic, so findings illustrate the analysis, not a real business.

## Tools
Power BI, Power Query.

