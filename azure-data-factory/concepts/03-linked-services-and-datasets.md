# Linked Services and Datasets

## Linked service
A linked service defines connection information to an external resource, such as Azure Blob Storage, ADLS Gen2, Azure SQL Database, or PostgreSQL. Authentication can use managed identity, service principal, key, or another supported method.

## Dataset
A dataset describes the data you want to use: for example, a file path and format, or a table in a database. It references a linked service.

## Difference
- Linked service: how to connect.
- Dataset: which data or location to use.

## Example
An ADLS linked service connects to a storage account. A delimited-text dataset points to `raw/orders/` and describes delimiter, encoding, and header settings.

## Parameterization
Use dataset parameters for dynamic folder paths, file names, schema, or table names. This avoids creating a separate dataset for every file.

## Practice
Create one storage linked service and parameterized datasets for CSV and Parquet data.
