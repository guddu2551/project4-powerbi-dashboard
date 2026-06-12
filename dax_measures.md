# DAX Measures — Power BI Sales Dashboard

Copy each measure exactly into Power BI.
Go to: Home → New Measure → paste the formula → press Enter

---

## REVENUE MEASURES

### Total Revenue
```
Total Revenue = SUM(powerbi_data[Revenue])
```

### Total Profit
```
Total Profit = SUM(powerbi_data[Profit])
```

### Profit Margin %
```
Profit Margin % = DIVIDE([Total Profit], [Total Revenue], 0)
```

### Total Orders
```
Total Orders = COUNTROWS(powerbi_data)
```

### Average Order Value
```
Avg Order Value = DIVIDE([Total Revenue], [Total Orders], 0)
```

### Completed Orders Only
```
Completed Revenue = 
CALCULATE(
    [Total Revenue],
    powerbi_data[Status] = "Completed"
)
```

---

## TIME INTELLIGENCE MEASURES

### Revenue Last Month
```
Revenue Last Month = 
CALCULATE(
    [Total Revenue],
    PREVIOUSMONTH(powerbi_data[OrderDate])
)
```

### Month over Month Growth %
```
MoM Growth % = 
DIVIDE(
    [Total Revenue] - [Revenue Last Month],
    [Revenue Last Month],
    0
)
```

### Revenue YTD (Year to Date)
```
Revenue YTD = 
CALCULATE(
    [Total Revenue],
    DATESYTD(powerbi_data[OrderDate])
)
```

---

## RANKING MEASURES

### Top Product
```
Top Product = 
FIRSTNONBLANK(
    TOPN(1,
        VALUES(powerbi_data[Product]),
        [Total Revenue], DESC
    ),
    1
)
```
