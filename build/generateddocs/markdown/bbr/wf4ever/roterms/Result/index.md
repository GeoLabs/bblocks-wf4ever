
# roterms:Result (Schema)

`ogc.bbr.wf4ever.roterms.Result` *v1.0*

Represents a result or outcome in the context of a Research Object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Result (roterms)

This Building Block represents the `Result` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#Result`
- **Description**: Represents a result or outcome in the context of a Research Object.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: Result
type: object
properties:
  name:
    type: string
    description: Title of the result.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the result.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  Result: http://purl.org/wf4ever/roterms#Result
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Result/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Result/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "Result": "roterms:Result",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Result/context.jsonld)

## Sources

* [Research Object Terms - Result](http://purl.org/wf4ever/roterms#Result)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/Result`

