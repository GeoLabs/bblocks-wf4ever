
# roterms:Comment (Schema)

`ogc.bbr.wf4ever.roterms.Comment` *v1.0*

Represents a comment in the context of a Research Object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Comment (roterms)

This Building Block represents the `Comment` class from the roterms ontology.

- **URI**: `http://purl.org/wf4ever/roterms#Comment`
- **Description**: Represents a comment in the context of a Research Object.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: Comment
type: object
properties:
  name:
    type: string
    description: Title of the comment.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Content of the comment.
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- description
x-jsonld-extra-terms:
  Comment:
    x-jsonld-id: http://purl.org/wf4ever/roterms#Comment
    x-jsonld-type: '@id'
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Comment/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Comment/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "Comment": {
      "@id": "roterms:Comment",
      "@type": "@id"
    },
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "prov": "http://www.w3.org/ns/prov#",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Comment/context.jsonld)

## Sources

* [Research Object Terms - Comment](http://purl.org/wf4ever/roterms#Comment)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/Comment`

