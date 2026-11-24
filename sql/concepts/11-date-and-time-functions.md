# SQL Server Date and Time Functions

## Common functions
- `GETDATE()`: current server date/time as `datetime`.
- `SYSDATETIME()`: higher-precision current server date/time.
- `DATEPART(part, date)`: returns a numeric date part.
- `DATENAME(part, date)`: returns a textual date part.
- `YEAR`, `MONTH`, `DAY`: extract components.
- `DATEADD(part, number, date)`: add or subtract an interval.
- `DATEDIFF(part, start, end)`: counts date-part boundaries crossed.
- `DATETRUNC(part, date)`: truncates to the start of a specified date part (SQL Server 2022+).
- `EOMONTH(date)`: returns the last date of the month.
- `CONVERT` / `CAST`: convert date/time values to other types.

```sql
SELECT
    OrderDate,
    YEAR(OrderDate) AS OrderYear,
    DATEADD(day, 7, OrderDate) AS DueDate,
    DATETRUNC(month, OrderDate) AS MonthStart,
    EOMONTH(OrderDate) AS MonthEnd
FROM Sales.Orders;
```

## Formatting
Prefer keeping dates as date/time types for filtering and calculations. Convert to text only for presentation.
```sql
SELECT CONVERT(char(10), OrderDate, 23) AS ISODate
FROM Sales.Orders;
```
Style `23` produces `yyyy-mm-dd`.

## Important distinction
`DATEDIFF(day, start, end)` counts midnight boundaries crossed, not always a precise elapsed 24-hour duration.

## Practice
1. Return orders from the current month.
2. Calculate days between order and delivery dates.
3. Return the first and last day of each order month.
