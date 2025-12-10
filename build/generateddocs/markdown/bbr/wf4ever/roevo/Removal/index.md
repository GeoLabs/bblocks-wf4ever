
# roevo:Removal (Schema)

`ogc.bbr.wf4ever.roevo.Removal` *v1.0*

Represents the removal of a resource in the context of Research Object evolution.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Removal (roevo)

This Building Block represents the `Removal` class from the roevo ontology.

- **URI**: `http://purl.org/wf4ever/roevo#Removal`
- **Description**: Represents the removal of a resource in the context of Research Object evolution.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roevo
title: Removal
type: object
properties:
  name:
    type: string
    description: Name of the removal.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the removal.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  Removal: http://purl.org/wf4ever/roevo#Removal
x-jsonld-vocab: http://purl.org/wf4ever/roevo#
x-jsonld-prefixes:
  roevo: http://purl.org/wf4ever/roevo#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/Removal/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/Removal/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roevo#",
    "Removal": "roevo:Removal",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roevo": "http://purl.org/wf4ever/roevo#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/Removal/context.jsonld)

## Sources

* [Research Object Evolution - Removal](http://purl.org/wf4ever/roevo#Removal)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roevo/Removal`

