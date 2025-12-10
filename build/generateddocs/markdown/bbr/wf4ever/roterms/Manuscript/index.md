
# roterms:Manuscript (Schema)

`ogc.bbr.wf4ever.roterms.Manuscript` *v1.0*

Represents a manuscript in the context of a Research Object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Manuscript (roterms)

This Building Block represents the `Manuscript` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#Manuscript`
- **Description**: Represents a manuscript in the context of a Research Object.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: Manuscript
type: object
properties:
  name:
    type: string
    description: Title of the manuscript.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the manuscript.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  Manuscript: http://purl.org/wf4ever/roterms#Manuscript
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Manuscript/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Manuscript/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "Manuscript": "roterms:Manuscript",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Manuscript/context.jsonld)

## Sources

* [Research Object Terms - Manuscript](http://purl.org/wf4ever/roterms#Manuscript)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/Manuscript`

