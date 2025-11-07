# wf4ever:Dataset

## Description

A **Dataset** is a specialization of `wfdesc:Artifact` representing a collection of data values or files that constitute a scientific dataset. Datasets are high-level data entities commonly consumed or produced by scientific workflows.

## Properties

- `@type` : Must include "Dataset"
- `title` : Dataset title or name
- `description` : Description of dataset contents
- `creator` : Dataset creator or owner
- `temporalCoverage` : Temporal extent (date range)
- `spatialCoverage` : Spatial extent (bounding box, region)

## Examples

### Remote Sensing Dataset

```json
{
  "@id": "#sentinel2-myanmar",
  "@type": "Dataset",
  "title": "Sentinel-2 Imagery - Myanmar Mangroves",
  "description": "Multispectral satellite imagery covering Myanmar mangrove regions",
  "temporalCoverage": "2025-08-01/2025-11-01",
  "spatialCoverage": {
    "west": 95.15,
    "south": 15.9,
    "east": 95.35,
    "north": 16.1
  }
}
```
