🍕 Pizza Sales Analytics Dashboard
📌 Short Description

An end-to-end data analytics project built with SQL + Power BI, designed to analyze pizza sales performance across multiple dimensions. SQL was used for data extraction, cleaning, and advanced queries, while Power BI was used for interactive dashboarding and business insights.

🛠️ Tech Stack

🗄️ SQL (MSSQL servers) – Data cleaning, transformations, and analysis queries

📊 Power BI Desktop – Data visualization & dashboard creation

📂 Power Query – ETL layer for shaping and cleaning data

🧠 DAX (Data Analysis Expressions) – KPIs, advanced calculations

📝 Data Modeling – Star schema (Orders, Customers, Pizzas, Categories)

📂 Data Source

Dataset: Pizza Sales Dataset (CSV format → Imported into SQL DB)

Order-level data with fields like:

Order ID, Date, Time

Pizza Name, Category, Size

Quantity, Price, Revenue

🔑 SQL Queries Used

Before moving to Power BI, SQL was used for data preparation + analysis.
Some example queries include:

1. Total Revenue & Orders
SELECT 
    SUM(quantity * price) AS total_revenue, 
    COUNT(DISTINCT order_id) AS total_orders 
FROM pizza_sales;

2. Top 5 Best-Selling Pizzas (by Revenue)
SELECT 
    pizza_name, 
    ROUND(SUM(quantity * price), 2) AS revenue
FROM pizza_sales
GROUP BY pizza_name
ORDER BY revenue DESC
LIMIT 5;

3. Bottom 5 Worst-Selling Pizzas (by Revenue)
SELECT 
    pizza_name, 
    ROUND(SUM(quantity * price), 2) AS revenue
FROM pizza_sales
GROUP BY pizza_name
ORDER BY revenue ASC
LIMIT 5;

4. Sales by Pizza Size
SELECT 
    pizza_size, 
    ROUND(SUM(quantity * price), 2) AS revenue
FROM pizza_sales
GROUP BY pizza_size
ORDER BY revenue DESC;

5. Peak Ordering Hours
SELECT 
    EXTRACT(HOUR FROM order_time) AS order_hour, 
    COUNT(order_id) AS total_orders
FROM pizza_sales
GROUP BY order_hour
ORDER BY total_orders DESC;


(More complex queries like monthly trends, category-level revenue, and average order values can be added in the repo under SQL Queries folder.)

🌟 Dashboard Features
🔹 Business Problem

Raw sales data lacked structure for insights — making it difficult to identify best-selling pizzas, peak hours, and underperforming categories.

🔹 Goal of the Dashboard

Provide real-time visibility into sales metrics

Support menu optimization & promotional strategies

Track order trends & revenue growth

🔹 Walkthrough of Key Visuals (in Power BI)

📌 KPIs: Revenue, Orders, Avg Order Value, Best Seller

📊 Category & Size Analysis (Donut + Stacked Chart)

📈 Sales Trends (Daily & Monthly)

🕒 Peak Hours of Orders (Line Chart)

🥇 Top 5 / Bottom 5 Pizzas (Bar Chart)

💡 Business Impact & Insights

✅ Identified best-selling pizzas to double down marketing

✅ Found underperforming pizzas → candidate for removal/re-pricing

✅ Optimized staff allocation based on peak demand hours

✅ Enabled data-driven decisions for pricing & promotions

🖼️ Screenshots

https://github.com/Imranshariff42/Pizza-Sales-Report/blob/main/Home%20page.png
