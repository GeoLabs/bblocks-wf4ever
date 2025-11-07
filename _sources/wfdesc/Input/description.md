# wfdesc:Input

## Description

An **Input** is a parameter that receives data into a workflow process. Inputs can receive data from:
- External sources (workflow inputs)
- Outputs of other processes (via DataLinks)
- Default values or configurations

## Class Hierarchy

```
wfdesc:Parameter
└── wfdesc:Input
```

## Properties

Inherits all properties from **Parameter**:

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `@type` | string | Yes | Must be "Input" |
| `@id` | URI | No | Unique identifier |
| `name` | string | No | Human-readable name |
| `description` | string | No | Description of what this input expects |

## Usage in Workflows

Inputs are declared using the `hasInput` property on a Process:

```json
{
  "@type": "Process",
  "name": "ImageProcessor",
  "hasInput": [
    {
      "@type": "Input",
      "@id": "#input-image",
      "name": "inputImage",
      "description": "The image to process"
    }
  ]
}
```

## Data Flow

Inputs can be connected to Outputs via DataLinks:

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
  "@type": "Input",
  "@id": "http://example.org/workflow/input/image",
  "name": "sourceImage",
  "description": "Source satellite image in GeoTIFF format"
}
```

## Related Classes

- **Parameter**: Base class (parent)
- **Output**: Complementary class for process outputs
- **DataLink**: Connects Outputs to Inputs
- **Process**: Container that has inputs via `hasInput` property
