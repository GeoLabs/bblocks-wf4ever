
# roterms:Review (Schema)

`ogc.bbr.wf4ever.roterms.Review` *v1.0*

Represents a review or examination associated with a Research Object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Review (roterms)

This Building Block represents the `Review` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#Review`
- **Description**: Represents a review or examination associated with a Research Object.
## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: Review
type: object
properties:
  name:
    type: string
    description: Title of the review.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the review.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  Review: http://purl.org/wf4ever/roterms#Review
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Review/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Review/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "Review": "roterms:Review",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Review/context.jsonld)

## Sources

* [Research Object Terms - Review](http://purl.org/wf4ever/roterms#Review)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/Review`

