
# roevo:VersionableResource (Schema)

`ogc.bbr.wf4ever.roevo.VersionableResource` *v1.0*

A resource within an RO that can be versioned with change specifications.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# roevo:VersionableResource

A resource within a Research Object that can be versioned.

- Purpose: model items that change across RO versions.
- Typical relations: `roevo:hasVersion`, `roevo:isVersionOf`.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: A resource that can have versions and associated changes
type: object
properties:
  '@id':
    type: string
    format: uri
    description: Identifier of the versionable resource
  '@type':
    type: string
    description: The RDF type of this object (roevo:VersionableResource)
  name:
    type: string
    description: Name of the resource
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the resource
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- '@id'
x-jsonld-extra-terms:
  VersionableResource: http://purl.org/wf4ever/roevo#VersionableResource
x-jsonld-vocab: http://purl.org/wf4ever/roevo#
x-jsonld-prefixes:
  roevo: http://purl.org/wf4ever/roevo#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/VersionableResource/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/VersionableResource/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roevo#",
    "VersionableResource": "roevo:VersionableResource",
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
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/VersionableResource/context.jsonld)

## Sources

* [Research Object Evolution Ontology - VersionableResource](http://purl.org/wf4ever/roevo#VersionableResource)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roevo/VersionableResource`

