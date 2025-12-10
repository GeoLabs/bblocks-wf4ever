
# roevo:SnapshotRO (Schema)

`ogc.bbr.wf4ever.roevo.SnapshotRO` *v1.0*

An immutable snapshot of a Research Object at a given time.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# roevo:SnapshotRO

An immutable snapshot of a Research Object at a specific point in time.

- Purpose: preserve a read-only state.
- Typical relations: `roevo:wasSnapshotOf` (links to the live RO), `roevo:createdAtTime` (timestamp).

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: An immutable snapshot of a Research Object
type: object
properties:
  '@id':
    type: string
    format: uri
    description: Identifier of the snapshot
  '@type':
    type: string
    description: The RDF type of this object (roevo:SnapshotRO)
  name:
    type: string
    description: Title of the snapshot
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of what is captured by the snapshot
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- '@id'
x-jsonld-extra-terms:
  SnapshotRO: http://purl.org/wf4ever/roevo#SnapshotRO
x-jsonld-vocab: http://purl.org/wf4ever/roevo#
x-jsonld-prefixes:
  roevo: http://purl.org/wf4ever/roevo#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/SnapshotRO/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/SnapshotRO/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roevo#",
    "SnapshotRO": "roevo:SnapshotRO",
    "@id": {
      "@context": {}
    },
    "@type": {
      "@context": {}
    },
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roevo": "http://purl.org/wf4ever/roevo#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/SnapshotRO/context.jsonld)

## Sources

* [Research Object Evolution Ontology - SnapshotRO](http://purl.org/wf4ever/roevo#SnapshotRO)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roevo/SnapshotRO`

