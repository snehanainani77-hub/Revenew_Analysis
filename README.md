# Revenew_Analysis
Sales data analysis project using SQL, Excel, and Tableau.
BikeStores Sales Analysis

Project Overview

This project analyzes BikeStores sales data using SQL, Excel, and Tableau. The objective of the project is to extract and analyze sales information and present meaningful insights through interactive dashboards.

The project demonstrates the complete data analysis workflow, including data extraction using SQL and data visualization using Excel and Tableau.

Tools Used

- SQL Server Management Studio (SSMS)
- Microsoft SQL
- Microsoft Excel
- Tableau
- GitHub

SQL Data Analysis

SQL was used to extract and combine data from multiple tables in the BikeStores database.

The analysis uses the following tables:

- "sales.orders"
- "sales.customers"
- "sales.order_items"
- "production.products"
- "production.categories"
- "production.brands"
- "sales.stores"
- "sales.staffs"

The SQL query uses "JOIN" operations to combine data from multiple tables and calculate important sales metrics.

Key Data Extracted

- Order ID
- Customer Name
- Customer City and State
- Order Date
- Total Units Sold
- Revenue
- Product Name
- Category
- Brand
- Store Name
- Sales Representative

SQL Query

USE BikeStores;

SELECT
    ord.order_id,
    CONCAT(cus.first_name, ' ', cus.last_name) AS customers,
    cus.city,
    cus.state,
    ord.order_date,
    SUM(ite.quantity) AS total_units,
    SUM(ite.quantity * ite.list_price) AS revenue,
    pro.product_name,
    cat.category_name,
    bra.brand_name,
    sto.store_name,
    CONCAT(sta.first_name, ' ', sta.last_name) AS sales_rep

FROM sales.orders ord

JOIN sales.customers cus
    ON ord.customer_id = cus.customer_id

JOIN sales.order_items ite
    ON ord.order_id = ite.order_id

JOIN production.products pro
    ON ite.product_id = pro.product_id

JOIN production.categories cat
    ON pro.category_id = cat.category_id

JOIN production.brands bra
    ON pro.brand_id = bra.brand_id

JOIN sales.stores sto
    ON ord.store_id = sto.store_id

JOIN sales.staffs sta
    ON ord.staff_id = sta.staff_id

GROUP BY
    ord.order_id,
    CONCAT(cus.first_name, ' ', cus.last_name),
    cus.city,
    cus.state,
    ord.order_date,
    pro.product_name,
    cat.category_name,
    bra.brand_name,
    sto.store_name,
    CONCAT(sta.first_name, ' ', sta.last_name);

Excel Dashboard

The extracted data was exported to Microsoft Excel for further analysis and visualization.

The Excel dashboard was created to analyze sales performance and present key insights using charts and interactive elements.

Tableau Dashboard

A Tableau dashboard was also created to visualize the BikeStores sales data.

The dashboard provides an interactive view of sales performance and helps analyze data across different categories, products, locations, stores, and sales representatives.

Project Workflow

1. Extracted and combined data from the BikeStores database using SQL.
2. Used SQL JOIN operations to combine multiple tables.
3. Calculated total units sold and revenue.
4. Exported the processed data for visualization.
5. Created an interactive dashboard in Microsoft Excel.
6. Created a Tableau dashboard for additional data visualization and analysis.



Skills Demonstrated

- SQL
- SQL JOINs
- Data Extraction
- Data Aggregation
- Data Analysis
- Microsoft Excel
- Tableau
- Data Visualization
- Dashboard Creation

Author

Sneha Nainani
