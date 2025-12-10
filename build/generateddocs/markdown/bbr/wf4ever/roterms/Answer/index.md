
# roterms:Answer (Schema)

`ogc.bbr.wf4ever.roterms.Answer` *v1.0*

Represents an answer to a question in the context of a Research Object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Answer (roterms)

This Building Block represents the `Answer` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#Answer`
- **Description**: Represents an answer to a question in the context of a Research Object.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: Answer
type: object
properties:
  name:
    type: string
    description: Title of the answer.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Content of the answer.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- description
x-jsonld-extra-terms:
  Answer: http://purl.org/wf4ever/roterms#Answer
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Answer/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Answer/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "Answer": "roterms:Answer",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Answer/context.jsonld)

## Sources

* [Research Object Terms - Answer](http://purl.org/wf4ever/roterms#Answer)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/Answer`

