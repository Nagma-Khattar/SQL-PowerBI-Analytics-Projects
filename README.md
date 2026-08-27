# Retail Sales Power BI Dashboard

## Project Overview

This project is an end-to-end retail sales analytics solution developed using MySQL and Microsoft Power BI.

The objective is to analyze retail sales performance and provide management with an interactive dashboard for monitoring revenue, transactions, product performance, category performance, and year-over-year trends.

> **Note:** This project uses synthetic retail data created for portfolio and demonstration purposes. It does not contain confidential or proprietary company information.

## Tools & Technologies

- MySQL
- MySQL Workbench
- Microsoft Power BI Desktop
- Power Query
- DAX
- Data Modeling

## Data Source

The source data was stored in a MySQL database (`roms_db`) containing:

- Categories
- Products
- Sales

The Sales table contains 200 synthetic retail sales transactions across 2025 and 2026.

## Data Preparation

Power Query was used to:

- Connect Power BI to the MySQL database
- Validate data types
- Check data quality, nulls, and errors
- Remove unnecessary navigation columns
- Prepare the tables for data modeling

## Data Model

The model uses one-to-many relationships:

- Categories (1) → (*) Products
- Products (1) → (*) Sales
- DateTable (1) → (*) Sales

A dedicated DateTable was created in Power BI to support time-intelligence analysis.

![Data Model](Screenshots/data-model.png)

## DAX Measures

Key measures include:

- Total Revenue
- Total Quantity Sold
- Total Transactions
- Average Transaction Value
- Revenue Previous Year
- Revenue YoY Difference
- YoY Revenue Growth %

For example:

`Total Revenue = SUMX(Sales, Sales[Quantity] * Sales[UnitPrice])`

## Dashboard Features

The dashboard includes:

- Total Revenue KPI
- Total Quantity Sold KPI
- Total Transactions KPI
- Average Transaction Value KPI
- YoY Revenue Growth KPI
- Monthly Revenue Trend
- Revenue by Category
- Revenue by Product
- Product Performance analysis
- Interactive Year, Category, and Product slicers

## Dashboard

![Retail Sales Dashboard](Screenshots/dashboard.png)

## Key Insights

The dashboard enables users to:

- Monitor overall retail revenue and transaction performance
- Compare revenue across products and categories
- Identify high-performing products
- Analyze monthly sales trends
- Compare current-year performance with the previous year
- Dynamically filter analysis by year, category, and product

## Skills Demonstrated

- SQL and relational database concepts
- Power Query data preparation
- Data quality validation
- Data modeling and relationships
- DAX calculations
- Time intelligence
- KPI development
- Interactive dashboard design
- Business-oriented data visualization

## Project Structure

Retail-Sales-PowerBI/
- Data/
  - Categories.csv
  - Products.csv
  - Sales.csv
- Screenshots/
  - dashboard.png
  - data-model.png
- Retail-Sales-PowerBI.pbix
- README.md
