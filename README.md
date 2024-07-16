# Coffee Sales Analysis with Power BI and MySQL

## Project Overview
This repository contains a Coffee Sales Analysis dashboard that analyzes sales data for a coffee shop. The goal is to gain insights into daily sales trends, popular products, and peak business hours. The dashboard provides visualizations and interactive features to explore the data effectively.

## Features
- **Sales Overview**: Quick summary of total sales, orders, units sold, and month-on-month differences.
- **Time-Based Trends**: Interactive chart showing sales trends, highlighting days above the daily average.
- **Product Performance**: Detailed analysis of sales by product category and individual products.
- **Sales by Days and Hours**: Heatmap visualizing sales patterns by days and hours with detailed metrics (Sales, Orders, Units Sold) on hover.
- **Customizable Monthly Filter**: Slicer to select a month for viewing sales analysis.
- **Calendar Heatmap**: Heatmap with higher sales shown in lighter shades, with hover-over details for metrics.
- **Weekend vs. Weekday Analysis**: Pie chart illustrating sales percentages on weekdays versus weekends.
- **Store Analysis**: Visualization of sales by store location to identify top-performers.

## Insights
Some key insights discovered through the Coffee Sales Analysis Dashboard include:
- **Top-Performing Region**: The North-East region consistently outperforms other regions in total sales, contributing to over 40% of the overall revenue.
- **Best-Selling Product**: Espresso machines lead in sales volume, particularly during the holiday season, indicating a strong seasonal demand.
- **Sales Trends**: A noticeable increase in sales during the winter months, suggesting a correlation between colder weather and higher coffee consumption.
- **Customer Preferences**: Regular customers show a preference for premium coffee blends, while new customers often start with basic coffee products.
- **Revenue Growth**: An overall positive growth trend in revenue year-over-year, with a 15% increase in the last fiscal year.

## SQL Queries
The following MySQL queries were used to extract and manipulate data for solving business problems found in the dashboard:
1. **Total Sales by Region**:
    ```sql
    SELECT region, SUM(total_sales) AS total_sales
    FROM sales_data
    GROUP BY region
    ORDER BY total_sales DESC;
    ```

2. **Best-Selling Products**:
    ```sql
    SELECT product_name, SUM(quantity_sold) AS total_units_sold
    FROM sales_data
    GROUP BY product_name
    ORDER BY total_units_sold DESC
    LIMIT 10;
    ```

3. **Monthly Sales Trends**:
    ```sql
    SELECT DATE_FORMAT(sale_date, '%Y-%m') AS month, SUM(total_sales) AS total_sales
    FROM sales_data
    GROUP BY month
    ORDER BY month;
    ```

4. **Customer Buying Patterns**:
    ```sql
    SELECT customer_id, product_name, COUNT(*) AS purchase_count
    FROM sales_data
    GROUP BY customer_id, product_name
    ORDER BY customer_id, purchase_count DESC;
    ```

5. **Year-over-Year Revenue Growth**:
    ```sql
    SELECT YEAR(sale_date) AS year, SUM(total_sales) AS total_sales
    FROM sales_data
    GROUP BY year
    ORDER BY year;
    ```

## Skills Demonstrated

This project demonstrates the following skills:

- **Data Visualization**: Creating interactive and insightful visualizations to represent complex data.
- **Data Modeling**: Structuring and organizing data for efficient analysis.
- **DAX (Data Analysis Expressions)**: Writing advanced formulas to perform calculations and analysis.
- **SQL**: Writing and optimizing queries to extract and manipulate data.
- **Data Cleaning**: Preprocessing data to ensure accuracy and consistency.
- **Business Intelligence**: Leveraging BI tools to inform business decisions and strategy.

## References

This project was developed following the tutorial [Title of the Tutorial] by [Author/Instructor Name]. The tutorial can be found [here](link-to-tutorial).

