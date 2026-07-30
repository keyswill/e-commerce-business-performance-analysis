# Electronics Sales Performance Analysis

## Project Overview

This Excel project examines transaction-level electronics sales to determine which products and product categories drive revenue, how sales volume differs from revenue contribution, and where performance is concentrated across the catalog.

The final interactive dashboard summarizes **$5.64 million in revenue**, **29,018 unique orders**, and **33,969 units sold**. City and product-category slicers allow users to explore the results by market and product group.

![Electronics Sales Dashboard](visuals/electronics-sales-dashboard.png)

## Business Questions

- Which products generate the most revenue?
- Which product categories account for the largest share of sales?
- Do the highest-volume categories also generate the most revenue?
- How concentrated is revenue among the leading products?

## Key Findings

- **Laptops and phones generated 61% of total revenue.**
- The four leading products—MacBook Pro Laptop, iPhone, ThinkPad Laptop, and Google Phone—generated **58.6% of revenue**.
- MacBook Pro Laptop was the strongest individual product, producing approximately **$1.28 million** in revenue.
- Batteries led all categories with **9,597 units sold**, but contributed less than 1% of revenue.
- The results show why product performance should be evaluated using both unit volume and revenue rather than either measure alone.

## Data Cleaning

The raw file contained **30,394 rows**. Excel was used to:

- Remove 87 blank rows
- Remove 61 repeated header rows
- Remove 40 duplicate transaction records
- Convert quantity, price, and order-date fields to appropriate data types
- Split the combined order timestamp into date and time fields
- Parse purchase addresses into street, city, state, and ZIP-code fields
- Create `Order Total` as `Quantity Ordered × Price Each`
- Assign products to reporting categories for dashboard analysis

The resulting dataset contains **30,206 clean transaction lines**.

## Dashboard Features

- KPI summary for revenue, unique orders, and units sold
- Product-category comparison by units sold
- Revenue contribution by product category
- Top 10 products by revenue
- Interactive city and product-category slicers

## Tools and Skills

- **Microsoft Excel:** data cleaning, formulas, PivotTables, PivotCharts, slicers, dashboard design
- **Business analysis:** KPI definition, revenue-concentration analysis, product-performance comparison
- **Data visualization:** chart selection, analytical titles, interactive filtering, executive reporting

## Repository Contents

| Path | Description |
|---|---|
| [`dashboard/Electronics Sales Dashboard.xlsx`](dashboard/Electronics%20Sales%20Dashboard.xlsx) | Final interactive Excel workbook |
| [`visuals/electronics-sales-dashboard.png`](visuals/electronics-sales-dashboard.png) | Dashboard preview |
| [`data/raw/Updated_sales.csv`](data/raw/Updated_sales.csv) | Original source data |
| [`data/processed/ecommerce_sales_processed.csv`](data/processed/ecommerce_sales_processed.csv) | Cleaned transaction data |
| [`notes/data-cleaning-and-methodology.md`](notes/data-cleaning-and-methodology.md) | KPI definitions, cleaning log, assumptions, and limitations |

## Limitations

- The available records cover portions of April, May, August, and September 2019, so they should not be interpreted as a continuous monthly trend.
- The dataset does not include product cost, profit, margin, returns, discounts, customer identifiers, or inventory levels.
- Revenue comparisons are descriptive and do not establish product profitability.
- Orders containing multiple products appear across multiple transaction lines; the Unique Orders KPI therefore uses distinct Order IDs.

## How to Explore the Workbook

Download the [Excel dashboard](dashboard/Electronics%20Sales%20Dashboard.xlsx), open it in Microsoft Excel, and use the City and Product Category slicers to filter all connected charts.
