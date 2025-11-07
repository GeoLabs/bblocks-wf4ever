# wfprov:WorkflowEngine

## Description

A **WorkflowEngine** represents a software agent that executes workflows. The workflow engine is responsible for enacting workflow and process executions, managing the execution environment and resources.

## Properties

- `@id` : Unique identifier for the workflow engine
- `@type` : Must be WorkflowEngine
- `name` : Name of the workflow engine
- `version` : Version of the workflow engine
- `description` : Description of the workflow engine

## Relations

- Process runs and workflow runs reference the engine via `wfprov:wasEnactedBy`
- This is the inverse relationship: the engine enacts the executions

## Examples of engines

- ZOO-Project WPS
- Apache Airflow
- Nextflow
- Snakemake
- CWL Runner

## Example

```json
{
  "@id": "#zoo-wps-engine",
  "@type": "WorkflowEngine",
  "name": "ZOO-Project WPS",
  "version": "1.9.0",
  "description": "Open source WPS server with workflow execution capabilities"
}
```
