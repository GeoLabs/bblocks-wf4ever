
# roterms:Presentation (Schema)

`ogc.bbr.wf4ever.roterms.Presentation` *v1.0*

Represents a presentation in the context of a Research Object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Presentation (roterms)

This Building Block represents the `Presentation` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#Presentation`
- **Description**: Represents a presentation in the context of a Research Object.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: Presentation
type: object
properties:
  name:
    type: string
    description: Title of the presentation.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the presentation.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  Presentation: http://purl.org/wf4ever/roterms#Presentation
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Presentation/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Presentation/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "Presentation": "roterms:Presentation",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Presentation/context.jsonld)

## Sources

* [Research Object Terms - Presentation](http://purl.org/wf4ever/roterms#Presentation)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/Presentation`

