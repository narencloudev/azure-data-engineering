# Execute Pipeline activity

## Purpose
Calls another pipeline, allowing workflows to be modular and reusable.

## Example
A master pipeline calls a child ingestion pipeline and passes a source name and processing date.

## Watch out
Pass required parameters and decide whether the parent should wait for the child pipeline to finish.

## Exercise
Draw a parent pipeline that calls two child pipelines.
