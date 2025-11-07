# ro:FolderEntry

## Description

A **FolderEntry** is an entry in a folder that maps a name to a resource. FolderEntries provide the mapping between folder paths and actual resources, similar to file system directory entries.

## Properties

- `@id` : Unique identifier for the folder entry
- `@type` : Must be FolderEntry
- `entryName` : Name of this entry in the folder
- `proxyFor` : The resource that this entry represents

## Relations

- Contained in a `ro:Folder` (via inverse of `ro:hasEntry`)
- Represents a `ro:Resource` via `ore:proxyFor`

## Example

```json
{
  "@id": "data/.ro/entry-landsat",
  "@type": "FolderEntry",
  "entryName": "landsat_scene.tif",
  "proxyFor": "data/landsat_scene.tif"
}
```
