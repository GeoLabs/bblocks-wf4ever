
# roterms:Rating (Schema)

`ogc.bbr.wf4ever.roterms.Rating` *v1.0*

Represents a rating or score assigned to a Research Object or its components.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Rating (roterms)

This Building Block represents the `Rating` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#Rating`
- **Description**: Represents a rating or score assigned to a Research Object or its components.
## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: Rating
type: object
properties:
  name:
    type: string
    description: Title of the rating.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the rating.
    x-jsonld-id: http://purl.org/dc/terms/description
  value:
    type: number
    description: Value of the rating or score.
    x-jsonld-id: http://purl.org/wf4ever/roterms#value
required:
- name
- value
x-jsonld-extra-terms:
  Rating: http://purl.org/wf4ever/roterms#Rating
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Rating/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Rating/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "Rating": "roterms:Rating",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "value": "roterms:value",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Rating/context.jsonld)

## Sources

* [Research Object Terms - Rating](http://purl.org/wf4ever/roterms#Rating)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/Rating`

