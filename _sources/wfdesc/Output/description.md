# wfdesc:Output

## Description

An **Output** is a parameter that produces data from a workflow process. Outputs can:
- Produce final workflow results
- Feed data to inputs of other processes via DataLinks
- Be intermediate results in a workflow

## Class Hierarchy

```
wfdesc:Parameter
└── wfdesc:Output
```

## Properties

Inherits all properties from **Parameter**:

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `@type` | string | Yes | Must be "Output" |
| `@id` | URI | No | Unique identifier |
| `name` | string | No | Human-readable name |
| `description` | string | No | Description of what this output produces |

## Usage in Workflows

Outputs are declared using the `hasOutput` property on a Process:

```json
{
  "@type": "Process",
  "name": "ImageProcessor",
  "hasOutput": [
    {
      "@type": "Output",
      "@id": "#output-result",
      "name": "processedImage",
      "description": "The processed image result"
    }
  ]
}
```

## Data Flow

Outputs can be connected to Inputs via DataLinks:

```json
{
  "@type": "DataLink",
  "hasSource": {
    "@type": "Output",
    "@id": "#process1-output"
  },
  "hasSink": {
    "@type": "Input",
    "@id": "#process2-input"
  }
}
```

## Example

```json
{
  "@type": "Output",
  "@id": "http://example.org/workflow/output/ndvi",
  "name": "ndviResult",
  "description": "Calculated NDVI raster layer"
}
```

## Related Classes

- **Parameter**: Base class (parent)
- **Input**: Complementary class for process inputs
- **DataLink**: Connects Outputs to Inputs (Output is source)
- **Process**: Container that has outputs via `hasOutput` property
