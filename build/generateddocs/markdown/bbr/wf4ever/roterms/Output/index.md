
# roterms:Output (Schema)

`ogc.bbr.wf4ever.roterms.Output` *v1.0*

Represents an output in the context of a Research Object workflow or process.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Output (roterms)

This Building Block represents the `Output` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#Output`
- **Description**: Represents an output in the context of a Research Object workflow or process.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: Output
type: object
properties:
  name:
    type: string
    description: Name of the output.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the output.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  Output:
    x-jsonld-id: http://purl.org/wf4ever/roterms#Output
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

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Output/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Output/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "Output": {
      "@id": "roterms:Output",
      "@type": "@id"
    },
    "name": "dcterms:title",
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
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Output/context.jsonld)

## Sources

* [Research Object Terms - Output](http://purl.org/wf4ever/roterms#Output)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/Output`

