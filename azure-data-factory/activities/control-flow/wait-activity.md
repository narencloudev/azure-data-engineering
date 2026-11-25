# Wait activity

## Purpose
Pauses a pipeline for a configured duration.

## Example
Wait briefly before checking whether an upstream file has arrived.

## Watch out
A wait does not itself verify that a condition has been met. Pair it with a check when needed.

## Exercise
Explain why Wait alone is not a reliable file-arrival check.
