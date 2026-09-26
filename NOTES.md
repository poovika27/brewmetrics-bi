# Copilot Notes — BrewMetrics BI

## Total Sales

### Copilot Prompt
Create a DAX measure called Total Sales that calculates the sum of sales_amount from the Fact_Sales table.

### Copilot Suggestion
```DAX
Total Sales = SUM(Fact_Sales[sales_amount])