# wfdesc:DataLink

## Description

A **DataLink** represents a data flow connection between processes in a workflow. It describes how the output of one process is connected to the input of another process, defining the data dependencies between workflow steps.

## Properties

- `@id` : Unique identifier for the data link
- `@type` : Must be "DataLink"
- `hasSource` : Reference to the output parameter (wfdesc:Output) that provides the data
- `hasSink` : Reference to the input parameter (wfdesc:Input) that receives the data

## Relations

- Links a `wfdesc:Output` (source) to a `wfdesc:Input` (sink)
- Used by `wfdesc:Workflow` via `hasDataLink`
- Defines the data flow between processes

## Example

```json
{
  "@id": "#link-reproject-to-ndvi",
  "@type": "DataLink",
  "hasSource": "#reproject-output",
  "hasSink": "#ndvi-red-input"
}
```

This example shows a data link connecting the output of a reprojection process to the input of an NDVI calculation process.
