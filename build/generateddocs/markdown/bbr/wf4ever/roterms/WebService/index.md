
# roterms:WebService (Schema)

`ogc.bbr.wf4ever.roterms.WebService` *v1.0*

A web service referenced or used by the research object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# WebService (roterms)

Ce Building Block représente la classe `WebService` de l'ontologie roterms.

- **URI** : `http://purl.org/wf4ever/roterms#WebService`
- **Description** : Représente un service web dans le contexte des Research Objects.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: A web service used or referenced by the research object
type: object
properties:
  '@id':
    type: string
    format: uri
    description: Identifier
  '@type':
    type: string
    description: RDF type (roterms:WebService)
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
  WebService: http://purl.org/wf4ever/roterms#WebService
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/WebService/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/WebService/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "WebService": "roterms:WebService",
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
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/WebService/context.jsonld)

## Sources

* [Research Object Terms - WebService](http://purl.org/wf4ever/roterms#WebService)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/WebService`

