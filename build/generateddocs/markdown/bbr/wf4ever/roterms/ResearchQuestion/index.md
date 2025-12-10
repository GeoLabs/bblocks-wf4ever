
# roterms:ResearchQuestion (Schema)

`ogc.bbr.wf4ever.roterms.ResearchQuestion` *v1.0*

Represents a research question in the context of a Research Object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# ResearchQuestion (roterms)

This Building Block represents the `ResearchQuestion` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#ResearchQuestion`
- **Description**: Represents a research question in the context of a Research Object.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: ResearchQuestion
type: object
properties:
  name:
    type: string
    description: Title of the research question.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the research question.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  ResearchQuestion: http://purl.org/wf4ever/roterms#ResearchQuestion
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ResearchQuestion/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ResearchQuestion/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "ResearchQuestion": "roterms:ResearchQuestion",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ResearchQuestion/context.jsonld)

## Sources

* [Research Object Terms - ResearchQuestion](http://purl.org/wf4ever/roterms#ResearchQuestion)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/ResearchQuestion`

