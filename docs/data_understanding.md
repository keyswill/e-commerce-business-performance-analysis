# Data Understanding

**Status: Complete**

## Dataset Grain

> One cleaned row represents one product line within an order.

An order ID may appear on multiple rows when an order contains multiple products. This is why orders require a distinct count while revenue and units are summed at the line level.

## Reconciliation

| Step | Rows removed | Rows remaining |
|---|---:|---:|
| Raw imported rows | — | 30,394 |
| Blank rows | 87 | 30,307 |
| Repeated headers | 61 | 30,246 |
| Duplicate transaction records | 40 | 30,206 |

## Key Fields and Business Use

| Field | Business use | Data note |
|---|---|---|
| Order ID | Distinct order count | Repeats across multi-product orders |
| Product | Product ranking and category assignment | Product names define reporting groups |
| Quantity Ordered | Unit-volume analysis | Used in revenue calculation |
| Price Each | Unit-price input | Does not include product cost |
| Order Date | Date and time analysis | Records are not a continuous annual series |
| Purchase Address | City, state, and ZIP analysis | Parsed into reporting fields |
| Order Total | Gross revenue | Quantity Ordered × Price Each |
| Product Category | Category reporting | Derived from product name |

## Connection to Business Questions

| Business question | Fields | Measure | Interpretation limit |
|---|---|---|---|
| Which products drive revenue? | Product, Order Total | Product revenue and share | Revenue is not profit |
| Which products drive volume? | Product, Quantity Ordered | Units sold | High units may reflect low prices |
| How concentrated is revenue? | Product, Order Total | Top-product revenue share | No risk or margin data |
| How do markets differ? | Parsed city, Order Total, quantity | Filtered KPIs | Customer and market-size data unavailable |

## Validated Baseline

| KPI | Value |
|---|---:|
| Clean transaction lines | 30,206 |
| Total revenue | $5,635,634.65 |
| Unique orders | 29,018 |
| Units sold | 33,969 |

## Analytical Readiness

The cleaned data supports descriptive revenue, order, unit, product, category, and city analysis. It does not support profitability, customer retention, inventory availability, fulfillment performance, or complete monthly trend analysis.

## Related Documentation

- [Cleaning and methodology](../notes/data-cleaning-and-methodology.md)
- [Business Understanding](business_understanding.md)
