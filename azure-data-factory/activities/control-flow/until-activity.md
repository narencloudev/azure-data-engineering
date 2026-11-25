# Until activity

## Purpose
Repeats its inner activities until a condition becomes true or the configured timeout is reached.

## Example
Poll for a file or external process completion, then continue when ready.

## Watch out
Always set a sensible timeout and avoid a loop that can run indefinitely.

## Exercise
Design a polling loop with a maximum wait time and a clear failure path.
