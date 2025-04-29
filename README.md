# Sales-Insights-Dashboard
## Project Objective 
To create an interactive Power BI dashboard that provides quick insights into sales performance, highlights top markets, customers, and products, and helps track revenue trends over time for better business decisions.
## Project Structure 
### Data Collection 
Data for this dashboard is collected directly from a MySQL database, which stores detailed sales records across regions, products, and customers. This database is part of the organization’s operational systems and serves as the primary data source.nstead of exporting data manually or using a separate warehouse, Power BI is directly connected to the MySQL database. This enables:

Real-time data updates

Simplified architecture

Faster setup for dashboard development
### Data Analysis
The core data analysis for this project was conducted using SQL. Exploratory Data Analysis (EDA) was performed directly on the MySQL database to uncover trends, segment performance, and identify key business insights before building the Power BI dashboard.
#### SQL Queries Used For EDA
1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`

### Data Cleaning and Tranformation 
After SQL-based EDA, further data shaping was done in Power BI’s Power Query Editor to prepare the dataset for reporting.

Key Steps:

Removed unnecessary columns and renamed fields for clarity

Converted data types (e.g., date, number)

Filtered out nulls and invalid records

Extracted year and month from date fields

Created custom columns for time-based analysis
### Dashboard Building
This project features a Sales Insights Dashboard built using Power BI, connected directly to a MySQL database. It visualizes key sales metrics such as total revenue, sales quantity, revenue trends, top-performing markets, best-selling products, and high-value customers.The dashboard helps stakeholders quickly identify growth opportunities, monitor performance, and make informed business decisions through interactive and real-time insights.
Key Metrics Tracked:

Total Revenue

Sales Quantity

Revenue by Market

Sales by Product & Customer

Monthly Revenue Trends
### Key Insights
Total Revenue Achieved: ₹984.81M, with 2M units sold across all markets.

Top Markets:

Delhi NCR and Mumbai lead in both revenue and quantity sold.


Top Products:

Product 1 contributes the highest revenue at ₹468.95M.


Top Customers:

Electrostar Stores and Electronica Store are the highest revenue-generating customers.


Revenue Trends:

Consistent sales observed between 2017–2019, followed by a gradual decline in 2020.
 ### Technology Used
 Power BI for dashboarding and data modeling

MySQL as the primary data source

Power Query Editor for data cleaning and transformation

SQL for exploratory data analysis (EDA)

![Screenshot 2025-04-30 023210](https://github.com/user-attachments/assets/dba5347e-b9eb-48da-903a-fad683588e16)




