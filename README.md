# Sales Data Analysis
**Stack:** SQL + Excel + Power BI

## Overview
Analyzes two years (2024–2025) of retail order data — 6,000 orders across 5 regions
and 5 product categories — to surface revenue, profit, and discounting trends that
a sales/merchandising team could act on.

## Files
| File | Purpose |
|---|---|
| `sales_data.csv` | Raw dataset (6,000 rows, 13 columns) |
| `sales_analysis.sql` | 10 SQL queries: KPIs, monthly trend, region/category breakdowns, top products, discount impact, top customers, payment mix |
| `Sales_Data_Analysis_Dashboard.xlsx` | Excel dashboard: Raw Data table, formula-driven Summary sheet, and a Charts sheet (bar/pie/line) — all built with live `SUMIF` formulas so it recalculates if the data changes |

## Key columns
`OrderID, OrderDate, Region, Category, Product, Quantity, UnitPrice, DiscountPct, Revenue, Cost, Profit, PaymentMethod, CustomerID`

## How to reproduce in a real SQL database
1. Create the `sales` table (schema at the top of `sales_analysis.sql`).
2. Import `sales_data.csv`.
3. Run the queries — each is commented with what business question it answers.

## Power BI dashboard design
Suggested pages, built from the same tables the Excel Summary sheet already computes:
1. **Executive Overview** — KPI cards (Revenue, Profit, Margin %, Orders), monthly trend line, region map/bar.
2. **Category Deep Dive** — category revenue/margin bar, top 10 products table, discount-vs-margin scatter.
3. **Customer & Payment** — top customers table, payment method donut.

Import `sales_data.csv` directly as the Power BI data source (or point it at the SQL
table) and rebuild the same visuals using Power BI's native chart types — the
Excel Summary tables mirror exactly what each Power BI visual would aggregate.

## Key insights (from this synthetic dataset)
- Electronics drives the highest revenue per order but has the thinnest margin due to unit cost.
- Discounts above 20% are associated with a visibly lower profit margin band — worth testing tighter caps.
- Revenue is fairly balanced across regions, with no single region above ~23% share.
