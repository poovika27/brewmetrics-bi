# BrewMetrics BI Solution

A version-controlled Power BI analytics solution for BrewMetrics Coffee Co.

# BrewMetrics Coffee Sales Dashboard

A version-controlled Power BI analytics solution for BrewMetrics Coffee Co., developed using Power BI, GitHub, Git, DAX, and GitHub Copilot.

## Project Description

BrewMetrics Coffee Co. operates Flagship stores, Kiosks, and Drive-Thrus across four cities. This project develops a version-controlled Business Intelligence solution to analyze coffee sales performance, city-level performance, store formats, product trends, and transaction values.

The Power BI dashboard provides interactive analysis of sales performance and supports business decision-making through visualizations, filters, drill-downs, and DAX measures.

## Data Model

The source data is stored in `brewmetrics_sales.csv`.

The Power BI model follows a star-schema structure:

### Fact Table

**Fact_Sales**
- sale_id
- date
- city
- item
- store_format
- quantity
- unit_price
- sales_amount

### Dimension Tables

**Dim_Date**
- date
- month
- year
- month_year

**Dim_City**
- city

**Dim_Product**
- item

The dimension tables connect to the central `Fact_Sales` table using one-to-many relationships. This structure separates transaction data from descriptive dimensions and supports efficient filtering and analysis.

## DAX Measures

The report contains the following DAX measures:

- Total Sales
- MoM Growth
- Running Total
- City Sales Rank
- Avg Transaction Value

These measures support sales analysis, month-over-month comparison, cumulative sales tracking, city ranking, and transaction-value analysis.

## Dashboard

The dashboard includes:

- Cold Brew Sales by Month
- Sales Performance by City
- Store Format Performance by City
- City and store-format drill-down
- Interactive filtering

## Key Dashboard Insights

1. The dashboard records total sales of **$3,966,327.88** across the analyzed transactions.

2. **Bengaluru** records the highest city-level sales at **$1,119,895.31**, followed by Chennai at **$1,054,801.19** and Hyderabad at **$968,966.26**.

3. The dashboard also provides store-format level analysis within each city, allowing sales and average transaction value to be compared across Flagship, Kiosk, and Drive-Thru formats.

## Technologies Used

- Power BI Desktop
- Power BI Project (.pbip)
- Power Query
- DAX
- Git
- GitHub
- GitHub Copilot

## Repository Structure

- `BrewMetrics.pbip` – Power BI project
- `BrewMetrics.Report/` – Report definition
- `BrewMetrics.SemanticModel/` – Semantic model definition
- `brewmetrics_sales.csv` – Source dataset
- `NOTES.md` – GitHub Copilot suggestions and corrections
- `REFLECTION.md` – Project reflection
- `.gitignore` – Git ignore configuration