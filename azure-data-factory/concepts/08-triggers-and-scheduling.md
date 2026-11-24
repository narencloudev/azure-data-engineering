# ADF Triggers and Scheduling

A trigger starts a pipeline.

## Trigger types
- **Schedule trigger**: runs at configured times or intervals.
- **Tumbling window trigger**: processes fixed, contiguous time windows and supports dependencies and retry-oriented window management.
- **Event-based trigger**: starts when a supported storage event occurs.

## Trigger vs pipeline
A pipeline defines what to do. A trigger defines when or why to start it.

## Parameters
Triggers can pass values such as scheduled time, window start, or window end into pipeline parameters.

## Operational considerations
- Set the correct time zone and understand daylight-saving behavior.
- Avoid overlapping runs unless the pipeline supports concurrency.
- Plan late-arriving files and reruns.
- Monitor trigger state and pipeline runs.

## Practice
Create a daily schedule trigger and pass the scheduled date into a pipeline parameter.
