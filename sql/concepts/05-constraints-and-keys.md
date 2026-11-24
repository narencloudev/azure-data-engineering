# Constraints and Keys

Constraints enforce data rules in a table.

## Common constraints
- `PRIMARY KEY`: uniquely identifies each row; cannot contain NULL.
- `FOREIGN KEY`: enforces a relationship to a candidate/primary key in another table.
- `UNIQUE`: prevents duplicate values in the constrained key.
- `NOT NULL`: requires a value.
- `CHECK`: validates a condition.
- `DEFAULT`: supplies a value when one is not provided.

```sql
CREATE TABLE dbo.Employees (
    EmployeeID INT PRIMARY KEY,
    Email VARCHAR(255) UNIQUE,
    Salary DECIMAL(12,2) CHECK (Salary >= 0),
    IsActive BIT NOT NULL DEFAULT 1,
    DepartmentID INT,
    CONSTRAINT FK_Employees_Departments
        FOREIGN KEY (DepartmentID)
        REFERENCES dbo.Departments(DepartmentID)
);
```

## Key terminology
- **Candidate key**: a minimal column set that uniquely identifies a row.
- **Primary key**: the candidate key selected as the main identifier.
- **Alternate key**: another candidate key not selected as primary.
- **Composite key**: a key made from multiple columns.
- **Surrogate key**: generated identifier with no business meaning.
- **Natural key**: identifier that comes from the business domain.

## Why constraints matter
They protect data quality at the database boundary, even when multiple applications write to the same tables.

## Practice
Design a `Products` table with a primary key, unique SKU, non-negative price, and required product name.
