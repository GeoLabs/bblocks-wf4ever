# ro:ResearchObject

## Description

A **ResearchObject** groups together resources, data, methods, and contextual information. It provides a structured way to package research results with their provenance, making them portable, shareable, and preservable.

## Properties

- `@id` : Unique identifier for the research object
- `@type` : Must be ResearchObject
- `title` : Title of the research object
- `description` : Description of the research object
- `aggregates` : Array of resources aggregated in this research object
- `manifest` : The manifest describing this research object
- `created` : Creation date of the research object

## Relations

- Aggregates `ro:Resource` via `ore:aggregates`
- Has a `ro:Manifest` via `ro:manifest`
- Can contain a `ro:Folder` to organize resources
- Can have `ro:AggregatedAnnotation` to annotate resources

## Example

```json
{
  "@id": "./",
  "@type": "ResearchObject",
  "title": "NDVI Computation Research Object",
  "description": "Complete workflow and data for NDVI computation from Landsat imagery",
  "aggregates": [
    { "@id": "workflow/ndvi.cwl" },
    { "@id": "data/" },
    { "@id": "results/" }
  ],
  "manifest": ".ro/manifest.json",
  "created": "2025-11-07T10:00:00Z"
}
```
