
# roterms:WorkflowValue (Schema)

`ogc.bbr.wf4ever.roterms.WorkflowValue` *v1.0*

Represents a value associated with a workflow parameter in the context of a Research Object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# WorkflowValue (roterms)

This Building Block represents the `WorkflowValue` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#WorkflowValue`
- **Description**: Represents a value associated with a workflow parameter in the context of a Research Object.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: WorkflowValue
type: object
properties:
  name:
    type: string
    description: Name of the workflow value.
    x-jsonld-id: http://purl.org/dc/terms/title
  value:
    description: The actual value.
    x-jsonld-id: http://www.w3.org/1999/02/22-rdf-syntax-ns#value
required:
- value
x-jsonld-extra-terms:
  WorkflowValue:
    x-jsonld-id: http://purl.org/wf4ever/roterms#WorkflowValue
    x-jsonld-type: '@id'
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/
  rdf: http://www.w3.org/1999/02/22-rdf-syntax-ns#
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/WorkflowValue/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/WorkflowValue/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "WorkflowValue": {
      "@id": "roterms:WorkflowValue",
      "@type": "@id"
    },
    "name": "dcterms:title",
    "value": "rdf:value",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "rdf": "http://www.w3.org/1999/02/22-rdf-syntax-ns#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "prov": "http://www.w3.org/ns/prov#",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/WorkflowValue/context.jsonld)

## Sources

* [Research Object Terms - WorkflowValue](http://purl.org/wf4ever/roterms#WorkflowValue)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/WorkflowValue`

