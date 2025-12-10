
# roterms:Conclusion (Schema)

`ogc.bbr.wf4ever.roterms.Conclusion` *v1.0*

A conclusion drawn from evidence within the research object.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# roterms:Conclusion

A conclusion derived from evidence in the Research Object.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: A conclusion statement
type: object
properties:
  '@id':
    type: string
    format: uri
    description: Identifier
  '@type':
    type: string
    description: RDF type (roterms:Conclusion)
  name:
    type: string
    description: Title
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Narrative description
    x-jsonld-id: http://purl.org/dc/terms/description
required:
- '@id'
x-jsonld-extra-terms:
  Conclusion: http://purl.org/wf4ever/roterms#Conclusion
x-jsonld-vocab: http://purl.org/wf4ever/roterms#
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Conclusion/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Conclusion/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/roterms#",
    "Conclusion": "roterms:Conclusion",
    "@id": {
      "@context": {}
    },
    "@type": {
      "@context": {}
    },
    "name": "dcterms:title",
    "description": "dcterms:description",
    "roterms": "http://purl.org/wf4ever/roterms#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/Conclusion/context.jsonld)

## Sources

* [Research Object Terms - Conclusion](http://purl.org/wf4ever/roterms#Conclusion)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms/Conclusion`

