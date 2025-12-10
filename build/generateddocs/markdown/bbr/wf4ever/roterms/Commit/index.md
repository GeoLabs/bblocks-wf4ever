
# roterms:Commit (Schema)

`ogc.bbr.wf4ever.roterms.Commit` *v1.0*

Represents a version control commit in the context of a Research Object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Commit (roterms)

This Building Block represents the `Commit` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#Commit`
- **Description**: Represents a version control commit in the context of a Research Object.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: Commit
type: object
properties:
  name:
    type: string
    description: Commit message.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Detailed description of the commit.
    x-jsonld-id: http://purl.org/dc/terms/description
  commitId:
    type: string
    description: Unique identifier for the commit.
    x-jsonld-id: http://purl.org/dc/terms/identifier
required:
- commitId
x-jsonld-extra-terms:
  Commit: http://purl.org/wf4ever/roterms#Commit
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Commit/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Commit/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "Commit": "roterms:Commit",
    "name": "dcterms:title",
    "description": "dcterms:description",
    "commitId": "dcterms:identifier",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Commit/context.jsonld)

## Sources

* [Research Object Terms - Commit](http://purl.org/wf4ever/roterms#Commit)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/Commit`

