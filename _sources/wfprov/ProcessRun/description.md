# wfprov:ProcessRun

## Description

A **ProcessRun** represents an execution instance of a process. It captures what actually happened during the execution of a process described by `wfdesc:Process`, including the input artifacts used, output artifacts generated, and timing information.

## Properties

- `@id` : Unique identifier for the execution
- `@type` : Type of execution (ProcessRun or WorkflowRun)
- `describedByProcess` : Links to the process description (wfdesc:Process) that was executed
- `usedInput` : Array of input artifacts used
- `startedAtTime` : Start time of the execution
- `endedAtTime` : End time of the execution
- `wasPartOfWorkflowRun` : The workflow run that this process run was part of
- `wasEnactedBy` : The workflow engine that enacted this process run

## Relations

- Must be linked to a `wfdesc:Process` via `describedByProcess`
- Uses `wfprov:Artifact` via `usedInput`
- Output artifacts reference this ProcessRun via their `wasOutputFrom` property
- Can be part of a `wfprov:WorkflowRun` via `wasPartOfWorkflowRun`
- Can be enacted by a `wfprov:WorkflowEngine` via `wasEnactedBy`

## Example

```json
{
  "@id": "#ndvi-process-run-1",
  "@type": "ProcessRun",
  "describedByProcess": "#ndvi-process",
  "usedInput": [
    { "@id": "artifact/band4.tif" },
    { "@id": "artifact/band5.tif" }
  ],
  "startedAtTime": "2025-11-07T10:00:00Z",
  "endedAtTime": "2025-11-07T10:05:00Z",
  "wasPartOfWorkflowRun": "#ndvi-workflow-run-1",
  "wasEnactedBy": "#zoo-wps-engine"
}
```
