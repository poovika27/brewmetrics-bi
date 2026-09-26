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


## Measure 3: Running Total

### Copilot Prompt

Create a DAX measure called Running Total that calculates cumulative Total Sales over time using Dim_Date[date]. Use FILTER and ALLSELECTED so the running total respects the current report selections.

### Copilot Suggestion

```DAX
Running Total =
CALCULATE(
    [Total Sales],
    FILTER(
        ALLSELECTED(Dim_Date[date]),
        Dim_Date[date] <= MAX(Dim_Date[date])
    )
)
```


## Measure 4: City Sales Rank

### Copilot Prompt

Create a DAX measure called City Sales Rank that ranks cities by [Total Sales] using RANKX over ALL(Dim_City[city]), with the highest sales ranked 1.

### Copilot Suggestion

```DAX
City Sales Rank =
RANKX(
    ALL(Dim_City[city]),
    [Total Sales],
    ,
    DESC
)
```