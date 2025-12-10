
# roterms:DataCollection (Schema)

`ogc.bbr.wf4ever.roterms.DataCollection` *v1.0*

Represents a data collection in the context of a Research Object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# DataCollection (roterms)

This Building Block represents the `DataCollection` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#DataCollection`
- **Description**: Represents a data collection in the context of a Research Object.
## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: DataCollection
type: object
properties:
  name:
    type: string
    description: Title of the data collection.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the data collection.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  DataCollection:
    x-jsonld-id: http://purl.org/wf4ever/roterms#DataCollection
    x-jsonld-type: '@id'
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/DataCollection/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/DataCollection/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "DataCollection": {
      "@id": "roterms:DataCollection",
      "@type": "@id"
    },
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "prov": "http://www.w3.org/ns/prov#",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/DataCollection/context.jsonld)

## Sources

* [Research Object Terms - DataCollection](http://purl.org/wf4ever/roterms#DataCollection)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/DataCollection`

