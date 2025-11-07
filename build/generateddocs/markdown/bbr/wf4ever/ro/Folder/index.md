
# ro:Folder (Schema)

`ogc.bbr.wf4ever.ro.Folder` *v1.0*

A folder that organizes resources within a Research Object. Folders provide hierarchical structure, similar to filesystem directories, allowing logical grouping of related resources.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# ro:Folder

## Description

A **Folder** organizes resources within a Research Object. Folders provide a hierarchical structure, similar to file system directories, allowing logical grouping of related resources.

## Relations

- Contains `ro:FolderEntry` via `ro:hasEntry`
- Can be aggregated in a `ro:ResearchObject`
- Can contain other Folders (recursive structure)

## Examples

### Workflow folder
#### json
```json
{
  "@id": "workflow/",
  "@type": "Folder",
  "name": "Workflow Folder",
  "description": "Contains workflow definitions and configurations",
  "hasEntry": [
    { "@id": "workflow/.ro/entry-ndvi-cwl" },
    { "@id": "workflow/.ro/entry-config" }
  ]
}

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/ro/Folder/context.jsonld",
  "@id": "workflow/",
  "@type": "Folder",
  "name": "Workflow Folder",
  "description": "Contains workflow definitions and configurations",
  "hasEntry": [
    {
      "@id": "workflow/.ro/entry-ndvi-cwl"
    },
    {
      "@id": "workflow/.ro/entry-config"
    }
  ]
}
```

#### ttl
```ttl
@prefix dcterms: <http://purl.org/dc/terms/> .
@prefix ro: <http://purl.org/wf4ever/ro#> .

<file:///github/workspace/workflow/> a ro:Folder ;
    dcterms:description "Contains workflow definitions and configurations" ;
    dcterms:title "Workflow Folder" ;
    ro:hasEntry <file:///github/workspace/workflow/.ro/entry-config>,
        <file:///github/workspace/workflow/.ro/entry-ndvi-cwl> .


```


### KindGrove Outputs Folder
#### json
```json
{
  "@id": "urn:uuid:83c8708e-ccbd-494e-b939-1298b65b1539",
  "@type": "Folder",
  "name": "outputs",
  "description": "Output directory containing mangrove analysis results",
  "hasEntry": [
    {
      "@id": "urn:uuid:cef10a06-9879-4354-8543-833951388c61",
      "entryName": "biomass_map.tif"
    },
    {
      "@id": "urn:uuid:f03ce803-f175-437f-bc7a-3888a62c1d4e",
      "entryName": "statistics.json"
    }
  ]
}

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/ro/Folder/context.jsonld",
  "@id": "urn:uuid:83c8708e-ccbd-494e-b939-1298b65b1539",
  "@type": "Folder",
  "name": "outputs",
  "description": "Output directory containing mangrove analysis results",
  "hasEntry": [
    {
      "@id": "urn:uuid:cef10a06-9879-4354-8543-833951388c61",
      "entryName": "biomass_map.tif"
    },
    {
      "@id": "urn:uuid:f03ce803-f175-437f-bc7a-3888a62c1d4e",
      "entryName": "statistics.json"
    }
  ]
}
```

#### ttl
```ttl
@prefix dcterms: <http://purl.org/dc/terms/> .
@prefix ro: <http://purl.org/wf4ever/ro#> .

<urn:uuid:83c8708e-ccbd-494e-b939-1298b65b1539> a ro:Folder ;
    dcterms:description "Output directory containing mangrove analysis results" ;
    dcterms:title "outputs" ;
    ro:hasEntry <urn:uuid:cef10a06-9879-4354-8543-833951388c61>,
        <urn:uuid:f03ce803-f175-437f-bc7a-3888a62c1d4e> .

<urn:uuid:cef10a06-9879-4354-8543-833951388c61> ro:entryName "biomass_map.tif" .

<urn:uuid:f03ce803-f175-437f-bc7a-3888a62c1d4e> ro:entryName "statistics.json" .


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: A folder organizing resources in a Research Object
type: object
properties:
  '@id':
    type: string
    format: uri
    description: Unique identifier for the folder
  '@type':
    const: Folder
    description: Type must be Folder
  name:
    type: string
    description: Name of the folder
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the folder
    x-jsonld-id: http://purl.org/dc/terms/description
  hasEntry:
    type: array
    items:
      type: object
      properties:
        '@id':
          type: string
          format: uri
      required:
      - '@id'
    description: Entries contained in this folder
    x-jsonld-id: http://purl.org/wf4ever/ro#hasEntry
    x-jsonld-type: '@id'
    x-jsonld-container: '@set'
required:
- '@id'
- '@type'
x-jsonld-extra-terms:
  Folder: http://purl.org/wf4ever/ro#Folder
x-jsonld-vocab: http://purl.org/wf4ever/ro#
x-jsonld-prefixes:
  ro: http://purl.org/wf4ever/ro#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/ro/Folder/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/ro/Folder/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/ro#",
    "Folder": "ro:Folder",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "hasEntry": {
      "@id": "ro:hasEntry",
      "@type": "@id",
      "@container": "@set"
    },
    "ro": "http://purl.org/wf4ever/ro#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/ro/Folder/context.jsonld)

## Sources

* [Research Object Ontology - Folder](http://purl.org/wf4ever/ro#Folder)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/ro/Folder`

