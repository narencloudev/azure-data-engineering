# ADF Monitoring, Logging, and Alerts

## Built-in monitoring
ADF Monitor provides pipeline runs, activity runs, trigger runs, duration, status, and error details. Configure diagnostic settings when logs need to be sent to Azure Monitor/Log Analytics or another supported destination.

## Custom audit logging
A practical audit table may include:
- `RunID`
- `PipelineName`
- `ActivityName`
- `SourceName`
- `TargetName`
- `StartTime`
- `EndTime`
- `Status`
- `RowsRead`
- `RowsCopied`
- `ErrorMessage`

## Alerts and notifications
Use supported Azure monitoring/alerting integrations or a notification workflow to notify stakeholders about failures. Avoid placing credentials in pipeline text.

## Operational metrics
Track success rate, failure rate, duration, throughput, late arrivals, and data-quality failures.

## Practice
Create a run-log table and document which fields you would write at pipeline start, success, and failure.
