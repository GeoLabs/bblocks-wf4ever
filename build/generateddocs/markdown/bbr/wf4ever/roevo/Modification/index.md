
# roevo:Modification (Schema)

`ogc.bbr.wf4ever.roevo.Modification` *v1.0*

Represents the modification of a resource in the context of Research Object evolution.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Modification (roevo)

This Building Block represents the `Modification` class from the roevo ontology.

- **URI**: `http://purl.org/wf4ever/roevo#Modification`
- **Description**: Represents the modification of a resource in the context of Research Object evolution.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roevo
title: Modification
type: object
properties:
  name:
    type: string
    description: Name of the modification.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the modification.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  Modification: http://purl.org/wf4ever/roevo#Modification
x-jsonld-vocab: http://purl.org/wf4ever/roevo#
x-jsonld-prefixes:
  roevo: http://purl.org/wf4ever/roevo#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/Modification/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/Modification/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roevo#",
    "Modification": "roevo:Modification",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roevo": "http://purl.org/wf4ever/roevo#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/Modification/context.jsonld)

## Sources

* [Research Object Evolution - Modification](http://purl.org/wf4ever/roevo#Modification)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roevo/Modification`

