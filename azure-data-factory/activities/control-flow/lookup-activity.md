# Lookup activity

## Purpose
Reads a small result set or a single row/value from a supported source. Often used to retrieve configuration or control information.

## Example
Read enabled table names from a metadata table, then pass the output to a ForEach activity.

## Watch out
Lookup has output and size limits; it is not intended for bulk data movement.

## Exercise
Create a metadata query that returns three enabled source tables.
