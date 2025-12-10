
# roterms:Software (Schema)

`ogc.bbr.wf4ever.roterms.Software` *v1.0*

Software referenced or used within the research object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# roterms:Software

Software referenced or used within the research object.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Software referenced or used within the research object
type: object
properties:
  '@id':
    type: string
    format: uri
    description: Identifier
  '@type':
    type: string
    description: RDF type (roterms:Software)
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
  Software:
    x-jsonld-id: http://purl.org/wf4ever/roterms#Software
    x-jsonld-type: '@id'
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Software/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Software/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "Software": {
      "@id": "roterms:Software",
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
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Software/context.jsonld)

## Sources

* [Research Object Terms - Software](http://purl.org/wf4ever/roterms#Software)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/Software`

