# Numeric and Mathematical Functions

## Common functions
- `ABS(x)`: absolute value.
- `ROUND(x, length)`: rounds to a specified decimal position.
- `CEILING(x)`: smallest integer greater than or equal to x.
- `FLOOR(x)`: largest integer less than or equal to x.
- `POWER(x, y)`: x raised to y.
- `SQRT(x)`: square root.
- `SIGN(x)`: returns -1, 0, or 1 according to sign.
- `RAND()`: pseudo-random float.

```sql
SELECT
    Amount,
    ROUND(Amount, 2) AS RoundedAmount,
    ABS(Amount) AS AbsoluteAmount,
    CEILING(Amount) AS RoundedUp
FROM Sales.Payments;
```

## Precision matters
Use `DECIMAL(p,s)` for exact decimal business values. Floating-point types are approximate and can produce small representation differences.

## Practice
Test `ROUND`, `CEILING`, `FLOOR`, `SIGN`, and `ABS` with positive, negative, and decimal inputs.
