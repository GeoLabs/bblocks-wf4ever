
# roterms:QualityAnnotation (Schema)

`ogc.bbr.wf4ever.roterms.QualityAnnotation` *v1.0*

Quality annotation associated with a Research Object or its components.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# QualityAnnotation (roterms)

This Building Block represents the `QualityAnnotation` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#QualityAnnotation`
- **Description**: Quality annotation associated with a Research Object or its components.
## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: QualityAnnotation
type: object
properties:
  name:
    type: string
    description: Title of the quality annotation.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the quality annotation.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  QualityAnnotation: http://purl.org/wf4ever/roterms#QualityAnnotation
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/QualityAnnotation/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/QualityAnnotation/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "QualityAnnotation": "roterms:QualityAnnotation",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/QualityAnnotation/context.jsonld)

## Sources

* [Research Object Terms - QualityAnnotation](http://purl.org/wf4ever/roterms#QualityAnnotation)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/QualityAnnotation`

