# wfprov:WorkflowRun

## Description

A **WorkflowRun** represents an execution instance of a complete workflow. It is a specialized type of ProcessRun that represents the execution of a `wfdesc:Workflow`, containing multiple ProcessRuns for its sub-processes.

## Properties

Inherits all properties from `wfprov:ProcessRun` plus:

- `@type` : Must be WorkflowRun
- `describedByWorkflow` : Links to the workflow description (wfdesc:Workflow) that was executed
- `hadSubProcessRun` : Array of process runs that were part of this workflow execution
- `wasEnactedBy` : The workflow engine that executed this workflow

## Relations

- Extends `wfprov:ProcessRun`
- Must be linked to a `wfdesc:Workflow` via `describedByWorkflow`
- Contains `wfprov:ProcessRun` via `hadSubProcessRun`
- Can be executed by a `wfprov:WorkflowEngine` via `wasEnactedBy`

## Example

```json
{
  "@id": "#ndvi-workflow-run-1",
  "@type": "WorkflowRun",
  "describedByWorkflow": "#ndvi-workflow",
  "describedByProcess": "#ndvi-workflow",
  "startedAtTime": "2025-11-07T10:00:00Z",
  "endedAtTime": "2025-11-07T10:10:00Z",
  "hadSubProcessRun": [
    { "@id": "#reproject-run-1" },
    { "@id": "#ndvi-calc-run-1" }
  ],
  "wasEnactedBy": "#my-workflow-engine"
}
```
