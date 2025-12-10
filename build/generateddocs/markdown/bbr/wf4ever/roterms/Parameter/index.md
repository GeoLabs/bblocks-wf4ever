
# roterms:Parameter (Schema)

`ogc.bbr.wf4ever.roterms.Parameter` *v1.0*

Represents a parameter in the context of a Research Object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Parameter (roterms)

This Building Block represents the `Parameter` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#Parameter`
- **Description**: Represents a parameter in the context of a Research Object.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: Parameter
type: object
properties:
  name:
    type: string
    description: Name of the parameter.
    x-jsonld-id: http://purl.org/dc/terms/title
  value:
    description: Value of the parameter.
    x-jsonld-id: http://purl.org/wf4ever/roterms#value
  description:
    type: string
    description: Description of the parameter.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  Parameter:
    x-jsonld-id: http://purl.org/wf4ever/roterms#Parameter
    x-jsonld-type: '@id'
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  prov: http://www.w3.org/ns/prov#
  wfdesc: http://purl.org/wf4ever/wfdesc#

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Parameter/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Parameter/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "Parameter": {
      "@id": "roterms:Parameter",
      "@type": "@id"
    },
    "name": "dcterms:title",
    "value": "roterms:value",
    "description": "dcterms:description",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "prov": "http://www.w3.org/ns/prov#",
    "wfdesc": "http://purl.org/wf4ever/wfdesc#",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Parameter/context.jsonld)

## Sources

* [Research Object Terms - Parameter](http://purl.org/wf4ever/roterms#Parameter)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/Parameter`

