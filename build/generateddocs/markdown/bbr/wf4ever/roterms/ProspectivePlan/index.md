
# roterms:ProspectivePlan (Schema)

`ogc.bbr.wf4ever.roterms.ProspectivePlan` *v1.0*

A prospective plan outlining intended tasks or steps.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# roterms:ProspectivePlan

A plan with intended tasks or steps.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: A prospective plan
type: object
properties:
  '@id':
    type: string
    format: uri
    description: Identifier
  '@type':
    type: string
    description: RDF type (roterms:ProspectivePlan)
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
  ProspectivePlan: http://purl.org/wf4ever/roterms#ProspectivePlan
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ProspectivePlan/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ProspectivePlan/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "ProspectivePlan": "roterms:ProspectivePlan",
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
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ProspectivePlan/context.jsonld)

## Sources

* [Research Object Terms - ProspectivePlan](http://purl.org/wf4ever/roterms#ProspectivePlan)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/ProspectivePlan`

