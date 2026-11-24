# ADF Factory, Pipelines, and Activities

## Factory
The Data Factory is the top-level resource that contains pipelines, linked services, datasets, triggers, integration runtimes, and related artifacts.

## Pipeline
A pipeline groups activities into a workflow. It can include dependencies, parameters, variables, and control-flow logic.

## Activity
An activity performs one operation. Examples:
- Copy Data
- Lookup
- Get Metadata
- ForEach
- If Condition
- Execute Pipeline
- Stored Procedure
- Web
- Databricks Notebook
- Script

## Dependency conditions
An activity can run after another activity succeeds, fails, completes, or is skipped. Design dependencies deliberately so failures are not silently ignored.

## Example workflow
Lookup configuration → ForEach source → Copy Data → log result → send notification on failure.

## Practice
Create a pipeline with two activities and configure the second to run only when the first succeeds.
