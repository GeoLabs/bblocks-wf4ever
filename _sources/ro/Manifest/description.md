# ro:Manifest

## Description

A **Manifest** describes the structure and content of a Research Object. The manifest provides metadata about the Research Object, its aggregated resources, annotations, and organizational structure.

## Properties

- `@id` : Unique identifier for the manifest
- `@type` : Must be Manifest
- `describes` : The Research Object that this manifest describes
- `createdBy` : Agent who created this manifest
- `createdOn` : Creation date of the manifest

## Relations

- Describes a `ro:ResearchObject` via `ore:describes`
- Created by an agent (person or system) via `dcterms:creator`

## Example

```json
{
  "@id": ".ro/manifest.json",
  "@type": "Manifest",
  "describes": "../",
  "createdBy": "https://orcid.org/0000-0001-2345-6789",
  "createdOn": "2025-11-07T10:00:00Z"
}
```
