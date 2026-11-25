# Mapping Data Flow activity

## Purpose
Runs a visual data transformation built with Mapping Data Flows, such as filtering, deriving columns, joining, aggregating, and altering schemas.

## When to use
Use it when visual, scalable transformations are appropriate and the cost/runtime profile is acceptable.

## Example
Read customer records, remove rows with missing IDs, standardize a name column, and write curated output.

## Watch out
Data Flow uses managed Spark compute and can incur cost while debugging or running. Check pricing and use small test data. For simple transformations, SQL or another existing compute option may be more economical.

## Exercise
Design a flow that filters invalid rows and derives a `FullName` column.
