# Data Cleaning and Methodology

## Dataset Grain

Each cleaned row represents one product line within an order. An Order ID may therefore appear more than once when a customer purchased multiple products in the same order.

## Cleaning Reconciliation

| Step | Rows Removed | Rows Remaining |
|---|---:|---:|
| Raw imported rows | — | 30,394 |
| Remove completely blank rows | 87 | 30,307 |
| Remove repeated header rows | 61 | 30,246 |
| Remove duplicate transaction records | 40 | 30,206 |

## Derived Fields

| Field | Method |
|---|---|
| Date | Extracted from Order Date |
| Time | Extracted from Order Date |
| Address | Parsed from Purchase Address |
| City | Parsed from Purchase Address and trimmed |
| State | Parsed from state and ZIP-code segment |
| ZIP Code | Parsed and stored as a five-character value |
| Order Total | Quantity Ordered × Price Each |
| Product Category | Assigned from the product name for reporting |

## KPI Definitions

| KPI | Definition | Result |
|---|---|---:|
| Total Revenue | Sum of Order Total across clean transaction lines | $5,635,634.65 |
| Unique Orders | Distinct count of Order ID | 29,018 |
| Units Sold | Sum of Quantity Ordered | 33,969 |

## Analytical Notes

- Category and product revenue are calculated from `Order Total`.
- Units sold are calculated from `Quantity Ordered`.
- Product rankings use total revenue and are displayed in descending order.
- Laptops and phones together represent approximately 61% of total revenue.
- The four highest-revenue products represent approximately 58.6% of total revenue.

## Assumptions

- Each retained transaction line represents a completed sale.
- Listed unit prices and quantities are accurate.
- Revenue is gross sales revenue before costs, returns, taxes, and adjustments.

## Limitations

- The records primarily cover April and August 2019, with limited spillover records in May and September.
- No cost or profit data is available, so product profitability cannot be evaluated.
- No customer identifier is available, so retention, segmentation, and customer lifetime value cannot be analyzed.
- No inventory or fulfillment information is available, so stock availability and operational performance cannot be assessed.
