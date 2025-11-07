# wfdesc:Workflow

## Description

A **Workflow** is a composite process that orchestrates multiple sub-processes connected by data flow. Workflows are directed acyclic graphs (DAGs) where:
- **Nodes** are processes (sub-processes)
- **Edges** are data links (data flow)

Workflows inherit from **Process**, so they also have inputs and outputs that define their external interface.

## Class Hierarchy

```
wfdesc:Process
└── wfdesc:Workflow
```

## Properties

Inherits all properties from **Process**, plus:

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `@type` | string | Yes | Must be "Workflow" |
| `@id` | URI | No | Unique identifier |
| `name` | string | No | Human-readable name |
| `description` | string | No | What the workflow does |
| `hasInput` | array | No | Workflow-level inputs |
| `hasOutput` | array | No | Workflow-level outputs |
| `hasSubProcess` | array | No | Processes within the workflow |
| `hasDataLink` | array | No | Data connections between processes |

## Workflow Structure

A workflow has two main components:

### 1. Sub-Processes (Nodes)
The computational steps in the workflow:

```json
"hasSubProcess": [
  {
    "@type": "Process",
    "@id": "#step1",
    "name": "Load Data"
  },
  {
    "@type": "Process",
    "@id": "#step2",
    "name": "Process Data"
  }
]
```

### 2. Data Links (Edges)
The data flow between processes:

```json
"hasDataLink": [
  {
    "@type": "DataLink",
    "hasSource": { "@id": "#step1-output" },
    "hasSink": { "@id": "#step2-input" }
  }
]
```

## Complete Example - Simple Pipeline

```json
{
  "@type": "Workflow",
  "@id": "#ndvi-workflow",
  "name": "NDVI Calculation Workflow",
  "description": "Loads satellite image, calculates NDVI, and exports result",
  "hasInput": [
    {
      "@type": "Input",
      "@id": "#workflow-input-image",
      "name": "satelliteImage"
    }
  ],
  "hasOutput": [
    {
      "@type": "Output",
      "@id": "#workflow-output-ndvi",
      "name": "ndviResult"
    }
  ],
  "hasSubProcess": [
    {
      "@type": "Process",
      "@id": "#load-process",
      "name": "Load Image",
      "hasInput": [
        {
          "@type": "Input",
          "@id": "#load-input",
          "name": "imagePath"
        }
      ],
      "hasOutput": [
        {
          "@type": "Output",
          "@id": "#load-output",
          "name": "loadedImage"
        }
      ]
    },
    {
      "@type": "Process",
      "@id": "#ndvi-process",
      "name": "Calculate NDVI",
      "hasInput": [
        {
          "@type": "Input",
          "@id": "#ndvi-input",
          "name": "image"
        }
      ],
      "hasOutput": [
        {
          "@type": "Output",
          "@id": "#ndvi-output",
          "name": "ndviLayer"
        }
      ]
    }
  ],
  "hasDataLink": [
    {
      "@type": "DataLink",
      "@id": "#link-load-to-ndvi",
      "hasSource": { "@id": "#load-output" },
      "hasSink": { "@id": "#ndvi-input" }
    }
  ]
}
```

## Workflow Patterns

### Sequential Pipeline
```
Process1 --> Process2 --> Process3
```

### Parallel Branches (Fan-out)
```
         /--> Process2 -->\\
Process1 --> Process3 --> Process5
         \\--> Process4 -->/ 
```

### Data Aggregation (Fan-in)
```
Process1 -->\\
Process2 --> Process4
Process3 -->/
```

## Nested Workflows

Workflows can contain other workflows as sub-processes:

```json
{
  "@type": "Workflow",
  "name": "Main Workflow",
  "hasSubProcess": [
    {
      "@type": "Workflow",
      "name": "Sub-Workflow",
      "hasSubProcess": [ /* ... */ ]
    }
  ]
}
```

## Workflow as a Black Box

From the outside, a workflow looks like a single process:
- Defined interface (hasInput, hasOutput)
- Internal structure hidden (hasSubProcess, hasDataLink)
- Can be reused as a component in larger workflows

## Related Classes

- **Process**: Parent class (Workflow is a specialized Process)
- **DataLink**: Defines data flow between sub-processes
- **Input/Output**: Define workflow interface
