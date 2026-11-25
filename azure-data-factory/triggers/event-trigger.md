# Event trigger

## Purpose
Starts a pipeline in response to supported storage events, such as a blob being created or deleted.

## Best for
File-arrival workflows where processing should begin when a file event occurs.

## Example
When a new CSV lands in an incoming container, start the ingestion pipeline.

## Watch out
Configure event scope and filters carefully. Consider duplicate events, file naming, and whether the file is fully written before processing.

## Exercise
Design a file-arrival trigger for CSV files in an incoming folder.
