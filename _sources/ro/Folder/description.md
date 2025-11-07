# ro:Folder

## Description

A **Folder** organizes resources within a Research Object. Folders provide a hierarchical structure, similar to file system directories, allowing logical grouping of related resources.

## Properties

- `@id` : Unique identifier for the folder
- `@type` : Must be Folder
- `name` : Name of the folder
- `description` : Description of the folder
- `hasEntry` : Array of entries contained in this folder

## Relations

- Contains `ro:FolderEntry` via `ro:hasEntry`
- Can be aggregated in a `ro:ResearchObject`
- Can contain other Folders (recursive structure)

## Example

```json
{
  "@id": "data/",
  "@type": "Folder",
  "name": "Data Folder",
  "description": "Contains all input and output data",
  "hasEntry": [
    { "@id": "data/.ro/entry-1" },
    { "@id": "data/.ro/entry-2" }
  ]
}
```
