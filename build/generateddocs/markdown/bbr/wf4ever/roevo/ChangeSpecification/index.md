
# roevo:ChangeSpecification (Schema)

`ogc.bbr.wf4ever.roevo.ChangeSpecification` *v1.0*

A specification of changes (additions, removals, modifications) applied between versions.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# roevo:ChangeSpecification

A set of changes (additions, removals, modifications) between two versions.

- Purpose: describe what changed.
- Often referenced by `roevo:hasChangeLog`, `roevo:hasAdditions`, `roevo:hasRemovals`, `roevo:hasModifications`.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: A set of changes applied between two versions
type: object
properties:
  '@id':
    type: string
    format: uri
    description: Identifier of the change specification
  '@type':
    type: string
    description: The RDF type of this object (roevo:ChangeSpecification)
  name:
    type: string
    description: Human-readable name for the change set
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Details of the changes
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- '@id'
x-jsonld-extra-terms:
  ChangeSpecification: http://purl.org/wf4ever/roevo#ChangeSpecification
x-jsonld-vocab: http://purl.org/wf4ever/roevo#
x-jsonld-prefixes:
  roevo: http://purl.org/wf4ever/roevo#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/ChangeSpecification/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/ChangeSpecification/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roevo#",
    "ChangeSpecification": "roevo:ChangeSpecification",
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
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/ChangeSpecification/context.jsonld)

## Sources

* [Research Object Evolution Ontology - ChangeSpecification](http://purl.org/wf4ever/roevo#ChangeSpecification)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roevo/ChangeSpecification`

