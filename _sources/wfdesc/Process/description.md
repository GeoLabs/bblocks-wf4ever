# wfdesc:Process

## Description

A **Process** represents a unit of computation in a workflow. It is the base class that can be:
- An **atomic process**: A single computational task (e.g., running a command-line tool)
- A **Workflow**: A composite process containing sub-processes

Processes are characterized by their inputs (what data they consume) and outputs (what data they produce).

## Class Hierarchy

```
wfdesc:Process (base class)
└── wfdesc:Workflow (composite process with sub-processes)
```

## Properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `@type` | string | Yes | "Process" or "Workflow" |
| `@id` | URI | No | Unique identifier |
| `name` | string | No | Human-readable name |
| `description` | string | No | What the process does |
| `hasInput` | array | No | Input parameters (array of Input objects) |
| `hasOutput` | array | No | Output parameters (array of Output objects) |

## Process Interface

The interface of a process is defined by its inputs and outputs:

```json
{
  "@type": "Process",
  "@id": "#ndvi-calculator",
  "name": "NDVI Calculator",
  "description": "Calculates Normalized Difference Vegetation Index",
  "hasInput": [
    {
      "@type": "Input",
      "@id": "#input-nir",
      "name": "nearInfrared",
      "description": "Near-infrared band"
    },
    {
      "@type": "Input",
      "@id": "#input-red",
      "name": "redBand",
      "description": "Red band"
    }
  ],
  "hasOutput": [
    {
      "@type": "Output",
      "@id": "#output-ndvi",
      "name": "ndviLayer",
      "description": "Calculated NDVI raster"
    }
  ]
}
```

## Atomic vs Composite

### Atomic Process
- Performs a single computational task
- Cannot be decomposed further in the workflow model
- Examples: Run GDAL command, Execute Python script, Call web service

### Composite Process (Workflow)
- Contains sub-processes via `hasSubProcess`
- Has internal data flow via `hasDataLink`
- Can be treated as a black box via its inputs/outputs

## Example - Atomic Process

```json
{
  "@type": "Process",
  "@id": "http://example.org/processes/reproject",
  "name": "Reproject Raster",
  "description": "Reprojects a raster to a target CRS",
  "hasInput": [
    {
      "@type": "Input",
      "@id": "#input-raster",
      "name": "sourceRaster"
    },
    {
      "@type": "Input",
      "@id": "#input-crs",
      "name": "targetCRS"
    }
  ],
  "hasOutput": [
    {
      "@type": "Output",
      "@id": "#output-reprojected",
      "name": "reprojectedRaster"
    }
  ]
}
```

## Example - With Multiple Outputs

```json
{
  "@type": "Process",
  "@id": "#statistics-calculator",
  "name": "Statistics Calculator",
  "hasInput": [
    {
      "@type": "Input",
      "@id": "#input-data",
      "name": "inputData"
    }
  ],
  "hasOutput": [
    {
      "@type": "Output",
      "@id": "#output-mean",
      "name": "meanValue"
    },
    {
      "@type": "Output",
      "@id": "#output-stdev",
      "name": "standardDeviation"
    },
    {
      "@type": "Output",
      "@id": "#output-histogram",
      "name": "histogram"
    }
  ]
}
```

## Related Classes

- **Input**: Parameters that feed data into the process
- **Output**: Parameters that produce data from the process
- **Workflow**: Subclass that represents composite processes
- **DataLink**: Connects processes together in a workflow
