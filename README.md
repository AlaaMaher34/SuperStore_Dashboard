[README.md](https://github.com/user-attachments/files/32412706/README.md)
# Superstore Sales Analysis Dashboard

An Excel-based sales analysis of the **Sample Superstore** dataset (orders from 2016 to 2019). The workbook cleans and enriches the raw order data, summarizes it with PivotTables, and presents the key results in an interactive dashboard with slicers.

**Author:** Alaa Maher (ALX5 – DAT1, Session 4)

---

## Project Overview

The goal is to understand how the business performs across regions, product categories, customer segments, and time, and to surface the answers in one dashboard that non-technical stakeholders can filter themselves.

**Questions the dashboard answers**

- Which regions generate the most sales?
- How do sales change month to month?
- Which product categories drive (or drag down) profit?
- How are sales distributed across small, medium, and large orders?
- How do results differ by customer segment and shipping mode?

## Workbook Structure

| Sheet | Purpose |
|---|---|
| **Orders** | Main dataset: 9,994 order lines and 23 columns. |
| **Returns** | Lookup of returned orders (800 rows, 296 unique order IDs). |
| **People** | Regional managers: Anna Andreadi (West), Chuck Magee (East), Kelly Williams (Central), Cassandra Brandow (South). |
| **pivot analysis** | Five PivotTables and four charts that feed the dashboard. |
| **DashBoard** | Final presentation layer: KPI charts plus slicers. |

### Orders: data dictionary

| Column | Description |
|---|---|
| Row ID, Order ID | Row and order identifiers |
| Order Date, Ship Date | Order and shipping dates |
| Ship Mode | Second Class, Standard Class, First Class, Same Day |
| Customer ID, Customer Name, Segment | Customer details; segment is Consumer, Corporate, or Home Office |
| Country/Region, City, State, Postal Code, Region | Location (49 states; regions are East, West, Central, South) |
| Product ID, Category, Sub-Category, Product Name | Product hierarchy (3 categories, 17 sub-categories, 1,862 products) |
| Sales, Quantity, Discount, Profit | Transaction measures |
| **Profit Margin** *(added)* | Profit ÷ Sales |
| **Sales Category** *(added)* | Order-line size bucket: **Low** (under 100), **Medium** (100 to 499.99), **High** (500 and above) |

## Analysis Performed

1. **Data preparation:** added the calculated columns *Profit Margin* and *Sales Category* to the raw orders.
2. **PivotTables:** built on the Orders sheet to aggregate:
   - Sales by Region
   - Profit by Category
   - Sales by Segment
   - Sales by Order Month
   - Sales by Sales Category
3. **Charts:**
   - Bar chart: *Sales by Region*
   - Line chart: *Sales over Months*
   - Pie chart: *Profit by Category*
   - Pie chart: *Sales by Sales Category* (on the analysis sheet)
4. **Dashboard:** the first three charts are assembled under the title *SuperStore Analysis Dashboard*, with slicers for **Region, Category, Segment, and Ship Mode** so every view can be filtered interactively.

## Key Findings

- **Totals:** about **$2.30M in sales** and **$286K in profit** (roughly a 12.5% overall margin) across 5,009 orders from 793 customers.
- **Regions:** West leads on sales (~$725K), followed by East (~$679K), Central (~$501K), and South (~$392K).
- **Categories by profit:** Technology (~$145K) and Office Supplies (~$122K) generate most of the profit. Furniture contributes only ~$18K despite substantial sales.
- **Segments:** Consumer accounts for about half of sales (~$1.16M), followed by Corporate (~$706K) and Home Office (~$430K).
- **Order size:** High-value order lines (500 and above) make up roughly 64% of total sales.
- **Seasonality:** sales peak in the fourth quarter, with September, November, and December the strongest months in the monthly pivot.
- **Growth:** yearly sales rose from ~$484K (2016) to ~$733K (2019).

> **Note:** the monthly pivot totals ~$2.14M rather than the full $2.30M, so it appears to be filtered (January and February are not shown). Check the pivot's filter before quoting monthly figures.

## How to Use

1. Open the `.xlsx` file in **Microsoft Excel** (desktop version recommended; slicers and PivotCharts may not fully render in other spreadsheet apps).
2. Go to the **DashBoard** sheet and use the slicers to filter by Region, Category, Segment, or Ship Mode.
3. Open **pivot analysis** to see or modify the underlying PivotTables (right-click, then *Refresh* after any change to the Orders data).

## Tools

- Microsoft Excel: PivotTables, PivotCharts, Slicers, calculated columns, dashboard layout

## Data Source

Based on Tableau's public *Sample – Superstore* dataset, a fictional retail company's orders used for teaching and demonstration.

## Possible Next Steps

- Join the **Returns** sheet to Orders to measure return rate and its effect on profit by category or region.
- Add a **Sub-Category** profitability view, and check whether discounts are behind the loss-making lines (e.g., Furniture's low profit).
- Add KPI cards (total sales, total profit, margin, order count) at the top of the dashboard.
- Add year-over-year comparison and a **Ship Date vs. Order Date** delivery-time analysis.
