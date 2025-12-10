
# roterms:ScientificMethod (Schema)

`ogc.bbr.wf4ever.roterms.ScientificMethod` *v1.0*

A description of the scientific method or approach used.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# roterms:ScientificMethod

A description of the method or approach used in the study.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: A description of the scientific method or approach used
type: object
properties:
  '@id':
    type: string
    format: uri
    description: Identifier
  '@type':
    type: string
    description: RDF type (roterms:ScientificMethod)
  name:
    type: string
    description: Title
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Narrative description
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- '@id'
x-jsonld-extra-terms:
  ScientificMethod:
    x-jsonld-id: http://purl.org/wf4ever/roterms#ScientificMethod
    x-jsonld-type: '@id'
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ScientificMethod/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ScientificMethod/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "ScientificMethod": {
      "@id": "roterms:ScientificMethod",
      "@type": "@id"
    },
    "@id": {
      "@context": {}
    },
    "@type": {
      "@context": {}
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
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ScientificMethod/context.jsonld)

## Sources

* [Research Object Terms - ScientificMethod](http://purl.org/wf4ever/roterms#ScientificMethod)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/ScientificMethod`

