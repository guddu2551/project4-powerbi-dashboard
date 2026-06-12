# Power BI Sales Dashboard — 3-Page Executive Report

A professional 3-page Power BI dashboard built on 1,000 retail transactions.
Covers revenue KPIs, product performance, and regional analysis
with DAX measures, drill-through, and interactive slicers.

---

## Dashboard Pages

### Page 1 — Executive Summary
![Executive Summary](screenshots/page1_executive_summary.png)

Key metrics at a glance:
- Total Revenue, Total Profit, Profit Margin %, Total Orders KPI cards
- Monthly revenue trend line chart
- Revenue by segment donut chart
- Top 5 products bar chart

### Page 2 — Product Performance
![Product Performance](screenshots/page2_product_performance.png)

Deep dive into product and category data:
- Revenue and profit by product — clustered bar chart
- Category breakdown — donut chart
- Profit margin % by product — table with conditional formatting
- Revenue vs Cost comparison — stacked bar

### Page 3 — Regional Analysis
![Regional Analysis](screenshots/page3_regional_analysis.png)

Geographic and segment performance:
- Revenue by region — bar chart
- Region vs Category matrix
- Order status breakdown by region — stacked bar
- Customer segment performance — bar chart

---

## DAX Measures Used

| Measure | Formula |
|---------|---------|
| Total Revenue | SUM(Revenue) |
| Total Profit | SUM(Profit) |
| Profit Margin % | DIVIDE(Profit, Revenue) |
| MoM Growth % | DIVIDE(current - previous, previous) |
| Revenue YTD | CALCULATE with DATESYTD |
| Avg Order Value | DIVIDE(Revenue, Orders) |

See `dax_measures.md` for all formulas.

---

## Data Model

Single flat table (star schema with one fact table):
- 1,000 orders
- 10 products across 3 categories
- 15 customers across 4 regions
- Date range: Jan 2024 — Dec 2024

---

## Tools Used

| Tool | Purpose |
|------|---------|
| Power BI Desktop | Dashboard development |
| DAX | Calculated measures |
| Power Query | Data loading and transformation |

---

## How to Recreate

1. Download `powerbi_data.csv`
2. Open Power BI Desktop
3. Get Data → Text/CSV → select the file
4. Create measures from `dax_measures.md`
5. Build visuals following the screenshots

---

*Part of my Data Analyst portfolio — demonstrating Power BI dashboard development, DAX measures, and data visualisation skills.*
