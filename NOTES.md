# Copilot Notes — BrewMetrics BI

## Measure 1: Total Sales

### Copilot Prompt

Create a DAX measure called Total Sales that calculates the sum of sales_amount from the Fact_Sales table.

### Copilot Suggestion

```DAX
Total Sales = SUM(Fact_Sales[sales_amount]) 
```

## Measure 2: MoM Growth

### Copilot Prompt

Create a DAX measure called MoM Growth that calculates month-over-month sales growth using the Total Sales measure and the Dim_Date date column. Use DATEADD to compare the current month with the previous month.

### Copilot Suggestion

```DAX
MoM Growth =
DIVIDE(
    [Total Sales] - CALCULATE(
        [Total Sales],
        DATEADD(Dim_Date[date], -1, MONTH)
    ),
    CALCULATE(
        [Total Sales],
        DATEADD(Dim_Date[date], -1, MONTH)
    )
)
```