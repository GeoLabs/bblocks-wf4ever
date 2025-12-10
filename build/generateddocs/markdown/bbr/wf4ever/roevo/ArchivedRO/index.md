
# roevo:ArchivedRO (Schema)

`ogc.bbr.wf4ever.roevo.ArchivedRO` *v1.0*

A Research Object that has been archived and is immutable, with associated archival metadata.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# roevo:ArchivedRO

An archived, immutable Research Object.

- Purpose: preserve a long-term, fixed state.
- Typical relations: `roevo:wasArchivedFrom`, `roevo:archivedAtTime`, `roevo:archiveLocation`.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: An archived Research Object
type: object
properties:
  '@id':
    type: string
    format: uri
    description: Identifier of the archived research object
  '@type':
    type: string
    description: The RDF type of this object (roevo:ArchivedRO)
  name:
    type: string
    description: Title of the archived research object
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Narrative description
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- '@id'
x-jsonld-extra-terms:
  ArchivedRO: http://purl.org/wf4ever/roevo#ArchivedRO
x-jsonld-vocab: http://purl.org/wf4ever/roevo#
x-jsonld-prefixes:
  roevo: http://purl.org/wf4ever/roevo#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/ArchivedRO/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/ArchivedRO/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roevo#",
    "ArchivedRO": "roevo:ArchivedRO",
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
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/ArchivedRO/context.jsonld)

## Sources

* [Research Object Evolution Ontology - ArchivedRO](http://purl.org/wf4ever/roevo#ArchivedRO)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roevo/ArchivedRO`

