
# roterms:DataTransformation (Schema)

`ogc.bbr.wf4ever.roterms.DataTransformation` *v1.0*

Represents a data transformation in the context of a Research Object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# DataTransformation (roterms)

This Building Block represents the `DataTransformation` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#DataTransformation`
- **Description**: Represents a data transformation in the context of a Research Object.
## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: DataTransformation
type: object
properties:
  name:
    type: string
    description: Title of the data transformation.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the data transformation.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  DataTransformation:
    x-jsonld-id: http://purl.org/wf4ever/roterms#DataTransformation
    x-jsonld-type: '@id'
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/DataTransformation/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/DataTransformation/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "DataTransformation": {
      "@id": "roterms:DataTransformation",
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
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/DataTransformation/context.jsonld)

## Sources

* [Research Object Terms - DataTransformation](http://purl.org/wf4ever/roterms#DataTransformation)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/DataTransformation`

