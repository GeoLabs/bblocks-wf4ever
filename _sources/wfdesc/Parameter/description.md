# wfdesc:Parameter

## Description

A **Parameter** is the base class for describing parameters of workflow processes. In wfdesc, parameters represent any kind of data port that can be connected in a workflow.

## Class Hierarchy

```
wfdesc:Parameter (base class)
├── wfdesc:Input (input parameter)
├── wfdesc:Output (output parameter)
└── wfdesc:Configuration (configuration parameter)
```

## Properties

| Property | Type | Description |
|----------|------|-------------|
| `@type` | string | Must be "Parameter" (or a subclass) |
| `@id` | URI | Unique identifier for this parameter |
| `name` | string | Human-readable name |
| `description` | string | Description of the parameter's purpose |

## Usage

Parameters are typically not used directly but through their subclasses (Input, Output, Configuration). They represent the interface points of a Process.

## Example

```json
{
  "@type": "Parameter",
  "@id": "http://example.org/workflow/param1",
  "name": "dataParameter",
  "description": "A generic data parameter"
}
```

## Related Classes

- **Input**: A parameter that receives data into a process
- **Output**: A parameter that produces data from a process
- **Configuration**: A parameter that configures process behavior
- **Process**: The class that has parameters
