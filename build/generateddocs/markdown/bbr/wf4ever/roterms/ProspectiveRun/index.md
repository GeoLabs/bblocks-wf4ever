
# roterms:ProspectiveRun (Schema)

`ogc.bbr.wf4ever.roterms.ProspectiveRun` *v1.0*

Represents a prospective run of a workflow in the context of a Research Object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# ProspectiveRun (roterms)

This Building Block represents the `ProspectiveRun` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#ProspectiveRun`
- **Description**: Represents a prospective run of a workflow in the context of a Research Object.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: ProspectiveRun
type: object
properties:
  name:
    type: string
    description: Name of the prospective run.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the prospective run.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- name
x-jsonld-extra-terms:
  ProspectiveRun: http://purl.org/wf4ever/roterms#ProspectiveRun
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ProspectiveRun/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ProspectiveRun/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "ProspectiveRun": "roterms:ProspectiveRun",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/ProspectiveRun/context.jsonld)

## Sources

* [Research Object Terms - ProspectiveRun](http://purl.org/wf4ever/roterms#ProspectiveRun)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/ProspectiveRun`

