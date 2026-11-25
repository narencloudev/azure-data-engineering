# Script activity

## Purpose
Runs SQL scripts against supported data stores.

## When to use
Use it for SQL statements such as creating staging objects, cleanup, or simple database-side operations.

## Example
Run a SQL statement to delete old rows from a staging table before a reload.

## Watch out
Use least-privilege permissions and be careful with destructive statements. Prefer parameterized, reviewed scripts.

## Exercise
Describe a safe pre-load cleanup script and how you would validate its effect.
