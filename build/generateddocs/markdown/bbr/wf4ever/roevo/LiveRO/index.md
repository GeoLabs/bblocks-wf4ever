
# roevo:LiveRO (Schema)

`ogc.bbr.wf4ever.roevo.LiveRO` *v1.0*

A live Research Object that is mutable and can evolve over time before being snapshotted or archived.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# roevo:LiveRO

A live Research Object that is mutable and can evolve before being snapshotted or archived.

- Purpose: represent an actively maintained RO.
- Typical transitions: `roevo:hasVersion`, `roevo:wasSnapshotOf` (from a snapshot), archival via `roevo:wasArchivedFrom`.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: A live Research Object under active evolution
type: object
properties:
  '@id':
    type: string
    format: uri
    description: Identifier of the live research object
  '@type':
    type: string
    description: The RDF type of this object (roevo:LiveRO)
  name:
    type: string
    description: Title of the live research object
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Narrative description
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- '@id'
x-jsonld-extra-terms:
  LiveRO: http://purl.org/wf4ever/roevo#LiveRO
x-jsonld-vocab: http://purl.org/wf4ever/roevo#
x-jsonld-prefixes:
  roevo: http://purl.org/wf4ever/roevo#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/LiveRO/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/LiveRO/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roevo#",
    "LiveRO": "roevo:LiveRO",
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
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/LiveRO/context.jsonld)

## Sources

* [Research Object Evolution Ontology - LiveRO](http://purl.org/wf4ever/roevo#LiveRO)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roevo/LiveRO`

