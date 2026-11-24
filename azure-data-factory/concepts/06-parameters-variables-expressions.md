# ADF Parameters, Variables, and Dynamic Expressions

## Parameters
Parameters are inputs supplied to a pipeline, dataset, or linked service. They are intended to be set when the artifact is invoked and are not changed during that run.

## Variables
Variables are pipeline-level values that can be updated during execution. Examples include counters, accumulated strings, and flags. Be careful with parallel ForEach loops because shared variable updates can create race conditions.

## Expressions
ADF expressions create dynamic values using functions and references.
Examples:
```text
@pipeline().parameters.sourceFolder
@concat('raw/', pipeline().parameters.tableName, '/')
@formatDateTime(utcNow(), 'yyyy/MM/dd')
@activity('LookupConfig').output.value
```

## Dynamic content
Dynamic content can set file paths, query text, names, and activity properties. Validate expressions and escape values correctly when generating SQL or paths.

## Best practices
- Parameterize reusable pipelines.
- Keep environment-specific values out of hard-coded activity settings.
- Do not store secrets in plain-text parameters.
- Give parameters meaningful names and document expected formats.

## Practice
Build one pipeline that accepts `sourceFolder`, `fileName`, and `targetFolder`.
