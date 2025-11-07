# ro:Resource

## Description

A **Resource** represents a resource that can be aggregated in a Research Object. Resources represent any artifact that contributes to the research result, such as data files, workflows, documentation, or external references.

## Properties

- `@id` : Unique identifier for the resource
- `@type` : Type of the resource
- `name` : Name of the resource
- `description` : Description of the resource

## Relations

- Can be aggregated in a `ro:ResearchObject` via `ore:aggregates`
- Can be referenced by a `ro:FolderEntry`
- Can be the target of a `ro:AggregatedAnnotation`

## Example

```json
{
  "@id": "data/landsat_scene.tif",
  "@type": "Resource",
  "name": "Landsat 8 Scene",
  "description": "Satellite imagery from Landsat 8 for NDVI analysis"
}
```
