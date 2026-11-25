# Stored Procedure activity

## Purpose
Executes a stored procedure in a supported database.

## When to use
Use it when transformation or business logic already exists in SQL Server or another supported database.

## Example
After copying data into a staging table, call `dbo.usp_MergeOrders` to merge it into a target table.

## Watch out
Confirm the procedure exists, permissions are granted, parameters match, and transaction/error behavior is understood.

## Exercise
Write the steps for loading a staging table and then calling a stored procedure.
