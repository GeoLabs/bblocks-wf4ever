
# roterms:ExampleRun (Schema)

`ogc.bbr.wf4ever.roterms.ExampleRun` *v1.0*

Represents an example run of a workflow in the context of a Research Object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# ExampleRun (roterms)

This Building Block represents the `ExampleRun` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#ExampleRun`
- **Description**: Represents an example run of a workflow in the context of a Research Object.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: ExampleRun
type: object
properties:
  name:
    type: string
    description: Name of the example run.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the example run.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  ExampleRun: http://purl.org/wf4ever/roterms#ExampleRun
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ExampleRun/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ExampleRun/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "ExampleRun": "roterms:ExampleRun",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ExampleRun/context.jsonld)

## Sources

* [Research Object Terms - ExampleRun](http://purl.org/wf4ever/roterms#ExampleRun)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/ExampleRun`

