
# roevo:Addition (Schema)

`ogc.bbr.wf4ever.roevo.Addition` *v1.0*

Represents the addition of a resource in the context of Research Object evolution.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Addition (roevo)

This Building Block represents the `Addition` class from the roevo ontology.

- **URI**: `http://purl.org/wf4ever/roevo#Addition`
- **Description**: Represents the addition of a resource in the context of Research Object evolution.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roevo
title: Addition
type: object
properties:
  name:
    type: string
    description: Name of the addition.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the addition.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  Addition: http://purl.org/wf4ever/roevo#Addition
x-jsonld-vocab: http://purl.org/wf4ever/roevo#
x-jsonld-prefixes:
  roevo: http://purl.org/wf4ever/roevo#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/Addition/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/Addition/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roevo#",
    "Addition": "roevo:Addition",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roevo": "http://purl.org/wf4ever/roevo#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/Addition/context.jsonld)

## Sources

* [Research Object Evolution - Addition](http://purl.org/wf4ever/roevo#Addition)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roevo/Addition`

