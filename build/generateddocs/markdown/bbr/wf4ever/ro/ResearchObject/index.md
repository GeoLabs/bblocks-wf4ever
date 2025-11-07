
# ro:ResearchObject (Schema)

`ogc.bbr.wf4ever.ro.ResearchObject` *v1.0*

A Research Object that bundles resources, data, methods, and contextual information. It provides a structured way to package research outputs with their provenance, making them portable, shareable, and preservable.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# ro:ResearchObject

## Description

A **ResearchObject** groups together resources, data, methods, and contextual information. It provides a structured way to package research results with their provenance, making them portable, shareable, and preservable.

## Relations

- Aggregates `ro:Resource` via `ore:aggregates`
- Has a `ro:Manifest` via `ro:manifest`
- Can contain a `ro:Folder` to organize resources
- Can have `ro:AggregatedAnnotation` to annotate resources

## Examples

### NDVI Research Object
#### json
```json
{
  "@id": "./",
  "@type": "ResearchObject",
  "title": "NDVI Computation Research Object",
  "description": "Complete workflow and data for NDVI computation from Landsat imagery",
  "aggregates": [
    { "@id": "workflow/ndvi.cwl" },
    { "@id": "data/input/" },
    { "@id": "data/output/" },
    { "@id": "README.md" }
  ],
  "manifest": ".ro/manifest.json",
  "created": "2025-11-07T10:00:00Z"
}

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/ro/ResearchObject/context.jsonld",
  "@id": "./",
  "@type": "ResearchObject",
  "title": "NDVI Computation Research Object",
  "description": "Complete workflow and data for NDVI computation from Landsat imagery",
  "aggregates": [
    {
      "@id": "workflow/ndvi.cwl"
    },
    {
      "@id": "data/input/"
    },
    {
      "@id": "data/output/"
    },
    {
      "@id": "README.md"
    }
  ],
  "manifest": ".ro/manifest.json",
  "created": "2025-11-07T10:00:00Z"
}
```

#### ttl
```ttl
@prefix dcterms: <http://purl.org/dc/terms/> .
@prefix ore: <http://www.openarchives.org/ore/terms/> .
@prefix ro: <http://purl.org/wf4ever/ro#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<file:///github/workspace/> a ro:ResearchObject ;
    dcterms:created "2025-11-07T10:00:00+00:00"^^xsd:dateTime ;
    dcterms:description "Complete workflow and data for NDVI computation from Landsat imagery" ;
    dcterms:title "NDVI Computation Research Object" ;
    ro:manifest <file:///github/workspace/.ro/manifest.json> ;
    ore:aggregates <file:///github/workspace/README.md>,
        <file:///github/workspace/data/input/>,
        <file:///github/workspace/data/output/>,
        <file:///github/workspace/workflow/ndvi.cwl> .


```


### KindGrove Research Object
#### json
```json
{
  "@id": "arcp://uuid,f02b8997-a6b1-4909-9946-9129c2b3f10c/",
  "@type": "ResearchObject",
  "title": "KindGrove Mangrove Analysis Research Object",
  "description": "Complete research object containing workflow definition, execution provenance, input parameters, and output results for mangrove biomass analysis in Myanmar using Sentinel-2 imagery",
  "conformsTo": "https://w3id.org/cwl/prov/0.6.0",
  "created": "2025-11-03T15:14:17.166945",
  "createdBy": "urn:uuid:5b925446-32a4-4104-9724-fa7360e1ef60",
  "aggregates": [
    {
      "@id": "../workflow/packed.cwl",
      "name": "Workflow definition",
      "mediatype": "text/x+yaml; charset=\"UTF-8\""
    },
    {
      "@id": "../workflow/primary-job.json",
      "name": "Job parameters",
      "mediatype": "application/json"
    },
    {
      "@id": "../workflow/primary-output.json",
      "name": "Workflow outputs",
      "mediatype": "application/json"
    },
    {
      "@id": "../metadata/provenance/primary.cwlprov.jsonld",
      "name": "Execution provenance",
      "mediatype": "application/ld+json",
      "conformsTo": [
        "http://www.w3.org/TR/2013/REC-prov-o-20130430/",
        "https://w3id.org/cwl/prov/0.6.0"
      ]
    },
    {
      "@id": "urn:hash::sha1:e71003c6b7dd4093ce139ac0c51a6ba38d54a439",
      "name": "Output data file"
    }
  ],
  "manifest": "../metadata/manifest.json"
}

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/ro/ResearchObject/context.jsonld",
  "@id": "arcp://uuid,f02b8997-a6b1-4909-9946-9129c2b3f10c/",
  "@type": "ResearchObject",
  "title": "KindGrove Mangrove Analysis Research Object",
  "description": "Complete research object containing workflow definition, execution provenance, input parameters, and output results for mangrove biomass analysis in Myanmar using Sentinel-2 imagery",
  "conformsTo": "https://w3id.org/cwl/prov/0.6.0",
  "created": "2025-11-03T15:14:17.166945",
  "createdBy": "urn:uuid:5b925446-32a4-4104-9724-fa7360e1ef60",
  "aggregates": [
    {
      "@id": "../workflow/packed.cwl",
      "name": "Workflow definition",
      "mediatype": "text/x+yaml; charset=\"UTF-8\""
    },
    {
      "@id": "../workflow/primary-job.json",
      "name": "Job parameters",
      "mediatype": "application/json"
    },
    {
      "@id": "../workflow/primary-output.json",
      "name": "Workflow outputs",
      "mediatype": "application/json"
    },
    {
      "@id": "../metadata/provenance/primary.cwlprov.jsonld",
      "name": "Execution provenance",
      "mediatype": "application/ld+json",
      "conformsTo": [
        "http://www.w3.org/TR/2013/REC-prov-o-20130430/",
        "https://w3id.org/cwl/prov/0.6.0"
      ]
    },
    {
      "@id": "urn:hash::sha1:e71003c6b7dd4093ce139ac0c51a6ba38d54a439",
      "name": "Output data file"
    }
  ],
  "manifest": "../metadata/manifest.json"
}
```

#### ttl
```ttl
@prefix dcterms: <http://purl.org/dc/terms/> .
@prefix ore: <http://www.openarchives.org/ore/terms/> .
@prefix ro: <http://purl.org/wf4ever/ro#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<arcp://uuid,f02b8997-a6b1-4909-9946-9129c2b3f10c/> a ro:ResearchObject ;
    dcterms:created "2025-11-03T15:14:17.166945"^^xsd:dateTime ;
    dcterms:description "Complete research object containing workflow definition, execution provenance, input parameters, and output results for mangrove biomass analysis in Myanmar using Sentinel-2 imagery" ;
    dcterms:title "KindGrove Mangrove Analysis Research Object" ;
    ro:conformsTo "https://w3id.org/cwl/prov/0.6.0" ;
    ro:createdBy "urn:uuid:5b925446-32a4-4104-9724-fa7360e1ef60" ;
    ro:manifest <file:///github/metadata/manifest.json> ;
    ore:aggregates <file:///github/metadata/provenance/primary.cwlprov.jsonld>,
        <file:///github/workflow/packed.cwl>,
        <file:///github/workflow/primary-job.json>,
        <file:///github/workflow/primary-output.json>,
        <urn:hash::sha1:e71003c6b7dd4093ce139ac0c51a6ba38d54a439> .

<file:///github/metadata/provenance/primary.cwlprov.jsonld> ro:conformsTo "http://www.w3.org/TR/2013/REC-prov-o-20130430/",
        "https://w3id.org/cwl/prov/0.6.0" ;
    ro:mediatype "application/ld+json" ;
    ro:name "Execution provenance" .

<file:///github/workflow/packed.cwl> ro:mediatype "text/x+yaml; charset=\"UTF-8\"" ;
    ro:name "Workflow definition" .

<file:///github/workflow/primary-job.json> ro:mediatype "application/json" ;
    ro:name "Job parameters" .

<file:///github/workflow/primary-output.json> ro:mediatype "application/json" ;
    ro:name "Workflow outputs" .

<urn:hash::sha1:e71003c6b7dd4093ce139ac0c51a6ba38d54a439> ro:name "Output data file" .


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: A Research Object bundling resources and contextual information
type: object
properties:
  '@id':
    type: string
    format: uri
    description: Unique identifier for the research object
  '@type':
    const: ResearchObject
    description: Type must be ResearchObject
  title:
    type: string
    description: Title of the research object
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: Description of the research object
    x-jsonld-id: http://purl.org/dc/terms/description
  aggregates:
    type: array
    items:
      type: object
      properties:
        '@id':
          type: string
          format: uri
      required:
      - '@id'
    description: Resources aggregated in this research object
    x-jsonld-id: http://www.openarchives.org/ore/terms/aggregates
    x-jsonld-type: '@id'
    x-jsonld-container: '@set'
  manifest:
    type: string
    format: uri
    description: The manifest describing this research object
    x-jsonld-id: http://purl.org/wf4ever/ro#manifest
    x-jsonld-type: '@id'
  created:
    type: string
    format: date-time
    description: Creation date of the research object
    x-jsonld-id: http://purl.org/dc/terms/created
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#dateTime
required:
- '@id'
- '@type'
x-jsonld-extra-terms:
  ResearchObject: http://purl.org/wf4ever/ro#ResearchObject
x-jsonld-vocab: http://purl.org/wf4ever/ro#
x-jsonld-prefixes:
  ro: http://purl.org/wf4ever/ro#
  dcterms: http://purl.org/dc/terms/
  ore: http://www.openarchives.org/ore/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/ro/ResearchObject/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/ro/ResearchObject/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/ro#",
    "ResearchObject": "ro:ResearchObject",
    "title": "dcterms:title",
    "description": "dcterms:description",
    "aggregates": {
      "@id": "ore:aggregates",
      "@type": "@id",
      "@container": "@set"
    },
    "manifest": {
      "@id": "ro:manifest",
      "@type": "@id"
    },
    "created": {
      "@id": "dcterms:created",
      "@type": "http://www.w3.org/2001/XMLSchema#dateTime"
    },
    "ro": "http://purl.org/wf4ever/ro#",
    "dcterms": "http://purl.org/dc/terms/",
    "ore": "http://www.openarchives.org/ore/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/ro/ResearchObject/context.jsonld)

## Sources

* [Research Object Ontology - ResearchObject](http://purl.org/wf4ever/ro#ResearchObject)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/ro/ResearchObject`

