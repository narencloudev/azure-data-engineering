# NULL Handling and Data Type Conversion

## NULL-handling functions
- `ISNULL(expression, replacement)`: replaces NULL with a value; result type follows the first expression's type.
- `COALESCE(a, b, c)`: returns the first non-NULL expression; follows data type precedence.
- `NULLIF(a, b)`: returns NULL when a equals b.
- `TRY_CAST` / `TRY_CONVERT`: return NULL instead of raising a conversion error when conversion fails.

```sql
SELECT
    ISNULL(PhoneNumber, 'Unknown') AS Phone,
    COALESCE(WorkEmail, PersonalEmail, 'No email') AS PreferredEmail
FROM dbo.Customers;
```

## Avoid divide-by-zero
```sql
SELECT Revenue / NULLIF(Quantity, 0) AS UnitPrice
FROM Sales.ProductSales;
```

## Safe conversion
```sql
SELECT TRY_CONVERT(date, RawDateText, 23) AS ParsedDate
FROM staging.RawOrders;
```

## Practice
1. Replace missing phone numbers with a display label.
2. Safely convert a text date column.
3. Prevent division by zero in a ratio calculation.
