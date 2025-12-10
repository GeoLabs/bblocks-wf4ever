
# Research Object Evolution Ontology (roevo) (Schema)

`ogc.bbr.wf4ever.roevo` *v1.0*

The Research Object Evolution ontology (roevo) extends ro to capture lifecycle, versioning, and evolution of research objects using PROV-O.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Research Object Evolution Ontology (roevo)

## Overview

The Research Object Evolution ontology (roevo) extends the [ro ontology](http://purl.org/wf4ever/ro) to capture the lifecycle and versioning of research objects using [PROV-O](https://www.w3.org/TR/prov-o/).

This ontology enables tracking of:
- Version history and evolution of research objects
- Snapshots and archives of research objects at different points in time
- Relationships between different versions (derivation, revision, etc.)
- Lifecycle states and transitions

## Namespace

`http://purl.org/wf4ever/roevo#`

## Key Classes

### Core Evolution Classes

- **VersionableResource** - A resource that can have multiple versions
- **LiveRO** - A live (current/working) research object that can be modified
- **SnapshotRO** - An immutable snapshot of a research object at a point in time
- **ArchivedRO** - A long-term archived version of a research object

### Versioning Classes

- **VersionInfo** - Information about a specific version
- **ChangeSpecification** - Specification of changes between versions

## Key Properties

### Versioning Properties

- **hasVersion** - Links a versionable resource to its versions
- **isVersionOf** - Inverse of hasVersion
- **wasRevisionOf** - Links a version to its previous version
- **wasSnapshotOf** - Links a snapshot to the live RO it was created from
- **wasArchivedFrom** - Links an archive to the snapshot it was created from

### Temporal Properties

- **createdAtTime** - When a version was created
- **modifiedAtTime** - When a resource was last modified
- **archivedAtTime** - When a resource was archived

### Change Tracking Properties

- **hasChangeLog** - Links to a change log document
- **hasAdditions** - Resources added in this version
- **hasRemovals** - Resources removed in this version
- **hasModifications** - Resources modified in this version

## Usage Patterns

### Creating a Snapshot

```turtle
@prefix roevo: <http://purl.org/wf4ever/roevo#> .
@prefix ro: <http://purl.org/wf4ever/ro#> .
@prefix prov: <http://www.w3.org/ns/prov#> .

# Live research object
:myRO a roevo:LiveRO, ro:ResearchObject ;
    roevo:hasVersion :myRO-v1, :myRO-v2 .

# Snapshot created from live RO
:myRO-v1 a roevo:SnapshotRO, ro:ResearchObject ;
    roevo:wasSnapshotOf :myRO ;
    roevo:createdAtTime "2025-01-15T10:30:00Z"^^xsd:dateTime ;
    prov:wasRevisionOf :myRO-v0 .
```

### Tracking Evolution

```turtle
# Version 2 revised from version 1
:myRO-v2 a roevo:SnapshotRO ;
    roevo:wasSnapshotOf :myRO ;
    prov:wasRevisionOf :myRO-v1 ;
    roevo:createdAtTime "2025-02-20T14:00:00Z"^^xsd:dateTime ;
    roevo:hasChangeLog :changelog-v2 .

# Change specification
:changelog-v2 a roevo:ChangeSpecification ;
    roevo:hasAdditions :newWorkflow.cwl ;
    roevo:hasModifications :existingData.csv ;
    roevo:hasRemovals :oldScript.py .
```

### Archiving

```turtle
# Archived version for long-term preservation
:myRO-v1-archived a roevo:ArchivedRO ;
    roevo:wasArchivedFrom :myRO-v1 ;
    roevo:archivedAtTime "2025-12-31T23:59:59Z"^^xsd:dateTime ;
    roevo:archiveLocation <https://archive.example.org/ro/myRO-v1> .
```

## Integration with PROV-O

roevo uses PROV-O concepts to provide provenance of research object evolution:

- **prov:Entity** - Research objects and their versions are PROV entities
- **prov:wasRevisionOf** - Links between versions
- **prov:wasDerivedFrom** - Derivation relationships
- **prov:generatedAtTime** - When a version was created
- **prov:Agent** - Persons or organizations creating versions

## Lifecycle States

Research objects can transition through different lifecycle states:

1. **Draft/Live** (LiveRO) - Active development, can be modified
2. **Snapshot** (SnapshotRO) - Point-in-time immutable copy
3. **Archived** (ArchivedRO) - Long-term preservation copy

## Use Cases

### Scientific Reproducibility

Track different versions of experimental workflows and datasets to ensure reproducibility of scientific results.

### Collaborative Research

Enable multiple researchers to work on different versions of research objects while maintaining version history.

### Long-term Preservation

Create immutable archived versions for institutional repositories and digital preservation.

### Audit Trail

Maintain complete change history for compliance and quality assurance in regulated research domains.

## References

- [W3C PROV-O](https://www.w3.org/TR/prov-o/)
- [Research Object Ontology](http://purl.org/wf4ever/ro)
- [Wf4Ever Research Object Model](http://wf4ever.github.io/ro/)

## Examples

### Research Object Snapshot Example
#### json
```json
{
  "@context": "https://ogcincubator.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/context.jsonld",
  "@id": "http://example.org/ro/myRO-v1",
  "@type": ["roevo:SnapshotRO", "ro:ResearchObject"],
  "dcterms:title": "My Research Object - Version 1",
  "roevo:wasSnapshotOf": "http://example.org/ro/myRO",
  "roevo:createdAtTime": "2025-01-15T10:30:00Z",
  "prov:wasRevisionOf": "http://example.org/ro/myRO-v0",
  "aggregates": [
    {
      "@id": "workflow.cwl",
      "@type": "wfdesc:Workflow"
    },
    {
      "@id": "input-data.csv",
      "@type": "wf4ever:Dataset"
    }
  ]
}

```


### Research Object with Change Log
#### json
```json
{
  "@context": "https://ogcincubator.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/context.jsonld",
  "@id": "http://example.org/ro/myRO-v2",
  "@type": "roevo:SnapshotRO",
  "roevo:wasSnapshotOf": "http://example.org/ro/myRO",
  "roevo:createdAtTime": "2025-02-20T14:00:00Z",
  "prov:wasRevisionOf": "http://example.org/ro/myRO-v1",
  "roevo:hasChangeLog": {
    "@id": "changelog-v2",
    "@type": "roevo:ChangeSpecification",
    "roevo:hasAdditions": [
      "new-workflow-step.cwl",
      "additional-data.json"
    ],
    "roevo:hasModifications": [
      "existing-data.csv"
    ],
    "roevo:hasRemovals": [
      "old-script.py"
    ],
    "dcterms:description": "Added new processing step, updated data format, removed deprecated script"
  }
}

```


### Archived Research Object
#### json
```json
{
  "@context": "https://ogcincubator.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/context.jsonld",
  "@id": "http://example.org/ro/myRO-v1-archived",
  "@type": "roevo:ArchivedRO",
  "roevo:wasArchivedFrom": "http://example.org/ro/myRO-v1",
  "roevo:archivedAtTime": "2025-12-31T23:59:59Z",
  "roevo:archiveLocation": "https://archive.example.org/ro/myRO-v1",
  "dcterms:description": "Archived for long-term preservation",
  "dcterms:format": "application/zip"
}

```


### Live Research Object with Version History
#### json
```json
{
  "@context": "https://ogcincubator.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/context.jsonld",
  "@id": "http://example.org/ro/myRO",
  "@type": ["roevo:LiveRO", "ro:ResearchObject"],
  "dcterms:title": "My Research Object",
  "roevo:hasVersion": [
    "http://example.org/ro/myRO-v0",
    "http://example.org/ro/myRO-v1",
    "http://example.org/ro/myRO-v2"
  ],
  "roevo:modifiedAtTime": "2025-11-28T12:00:00Z",
  "dcterms:creator": {
    "@type": "foaf:Person",
    "foaf:name": "Dr. Jane Smith"
  }
}

```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roevo
title: Research Object Evolution Ontology
description: Schema for the Research Object Evolution ontology (roevo) providing lifecycle
  and versioning concepts
type: object
allOf:
- $ref: https://ogcincubator.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/ro/schema.json
properties:
  '@type':
    oneOf:
    - type: string
      enum:
      - roevo:LiveRO
      - roevo:SnapshotRO
      - roevo:ArchivedRO
      - roevo:VersionableResource
      - roevo:VersionInfo
      - roevo:ChangeSpecification
    - type: array
      items:
        type: string
  roevo:hasVersion:
    description: Links a versionable resource to its versions
    oneOf:
    - $ref: '#/$defs/ResourceReference'
    - type: array
      items:
        $ref: '#/$defs/ResourceReference'
  roevo:wasSnapshotOf:
    description: Links a snapshot to the live RO it was created from
    $ref: '#/$defs/ResourceReference'
  roevo:wasArchivedFrom:
    description: Links an archive to the snapshot it was created from
    $ref: '#/$defs/ResourceReference'
  roevo:createdAtTime:
    description: When a version was created
    type: string
    format: date-time
  roevo:modifiedAtTime:
    description: When a resource was last modified
    type: string
    format: date-time
  roevo:archivedAtTime:
    description: When a resource was archived
    type: string
    format: date-time
  roevo:hasChangeLog:
    description: Links to a change log document
    $ref: '#/$defs/ResourceReference'
  roevo:hasAdditions:
    description: Resources added in this version
    type: array
    items:
      $ref: '#/$defs/ResourceReference'
  roevo:hasRemovals:
    description: Resources removed in this version
    type: array
    items:
      $ref: '#/$defs/ResourceReference'
  roevo:hasModifications:
    description: Resources modified in this version
    type: array
    items:
      $ref: '#/$defs/ResourceReference'
$defs:
  ResourceReference:
    oneOf:
    - type: string
      format: uri
    - type: object
      required:
      - '@id'
      properties:
        '@id':
          type: string
          format: uri
x-jsonld-extra-terms:
  LiveRO: http://purl.org/wf4ever/roevo#LiveRO
  SnapshotRO: http://purl.org/wf4ever/roevo#SnapshotRO
  ArchivedRO: http://purl.org/wf4ever/roevo#ArchivedRO
  VersionableResource: http://purl.org/wf4ever/roevo#VersionableResource
  VersionInfo: http://purl.org/wf4ever/roevo#VersionInfo
  ChangeSpecification: http://purl.org/wf4ever/roevo#ChangeSpecification
  hasVersion:
    x-jsonld-id: http://purl.org/wf4ever/roevo#hasVersion
    x-jsonld-type: '@id'
  isVersionOf:
    x-jsonld-id: http://purl.org/wf4ever/roevo#isVersionOf
    x-jsonld-type: '@id'
  wasSnapshotOf:
    x-jsonld-id: http://purl.org/wf4ever/roevo#wasSnapshotOf
    x-jsonld-type: '@id'
  wasArchivedFrom:
    x-jsonld-id: http://purl.org/wf4ever/roevo#wasArchivedFrom
    x-jsonld-type: '@id'
  wasRevisionOf:
    x-jsonld-id: http://www.w3.org/ns/prov#wasRevisionOf
    x-jsonld-type: '@id'
  createdAtTime:
    x-jsonld-id: http://purl.org/wf4ever/roevo#createdAtTime
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#dateTime
  modifiedAtTime:
    x-jsonld-id: http://purl.org/wf4ever/roevo#modifiedAtTime
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#dateTime
  archivedAtTime:
    x-jsonld-id: http://purl.org/wf4ever/roevo#archivedAtTime
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#dateTime
  hasChangeLog:
    x-jsonld-id: http://purl.org/wf4ever/roevo#hasChangeLog
    x-jsonld-type: '@id'
  hasAdditions:
    x-jsonld-id: http://purl.org/wf4ever/roevo#hasAdditions
    x-jsonld-type: '@id'
    x-jsonld-container: '@set'
  hasRemovals:
    x-jsonld-id: http://purl.org/wf4ever/roevo#hasRemovals
    x-jsonld-type: '@id'
    x-jsonld-container: '@set'
  hasModifications:
    x-jsonld-id: http://purl.org/wf4ever/roevo#hasModifications
    x-jsonld-type: '@id'
    x-jsonld-container: '@set'
  archiveLocation:
    x-jsonld-id: http://purl.org/wf4ever/roevo#archiveLocation
    x-jsonld-type: '@id'
x-jsonld-prefixes:
  roevo: http://purl.org/wf4ever/roevo#
  prov: http://www.w3.org/ns/prov#
  xsd: http://www.w3.org/2001/XMLSchema#
  ro: http://purl.org/wf4ever/ro#
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "ResearchObject": "ro:ResearchObject",
    "Resource": "ro:Resource",
    "Folder": "ro:Folder",
    "FolderEntry": "ro:FolderEntry",
    "AggregatedAnnotation": "ro:AggregatedAnnotation",
    "Manifest": "ro:Manifest",
    "@type": {
      "@context": {}
    },
    "name": "rdfs:label",
    "aggregates": {
      "@id": "ore:aggregates",
      "@type": "@id"
    },
    "rootFolder": {
      "@id": "ro:rootFolder",
      "@type": "@id"
    },
    "entryName": "ro:entryName",
    "annotatesAggregatedResource": {
      "@id": "ro:annotatesAggregatedResource",
      "@type": "@id"
    },
    "manifest": {
      "@id": "ro:manifest",
      "@type": "@id"
    },
    "isDescribedBy": {
      "@id": "ore:isDescribedBy",
      "@type": "@id"
    },
    "LiveRO": "roevo:LiveRO",
    "SnapshotRO": "roevo:SnapshotRO",
    "ArchivedRO": "roevo:ArchivedRO",
    "VersionableResource": "roevo:VersionableResource",
    "VersionInfo": "roevo:VersionInfo",
    "ChangeSpecification": "roevo:ChangeSpecification",
    "hasVersion": {
      "@id": "roevo:hasVersion",
      "@type": "@id"
    },
    "isVersionOf": {
      "@id": "roevo:isVersionOf",
      "@type": "@id"
    },
    "wasSnapshotOf": {
      "@id": "roevo:wasSnapshotOf",
      "@type": "@id"
    },
    "wasArchivedFrom": {
      "@id": "roevo:wasArchivedFrom",
      "@type": "@id"
    },
    "wasRevisionOf": {
      "@id": "prov:wasRevisionOf",
      "@type": "@id"
    },
    "createdAtTime": {
      "@id": "roevo:createdAtTime",
      "@type": "xsd:dateTime"
    },
    "modifiedAtTime": {
      "@id": "roevo:modifiedAtTime",
      "@type": "xsd:dateTime"
    },
    "archivedAtTime": {
      "@id": "roevo:archivedAtTime",
      "@type": "xsd:dateTime"
    },
    "hasChangeLog": {
      "@id": "roevo:hasChangeLog",
      "@type": "@id"
    },
    "hasAdditions": {
      "@id": "roevo:hasAdditions",
      "@type": "@id",
      "@container": "@set"
    },
    "hasRemovals": {
      "@id": "roevo:hasRemovals",
      "@type": "@id",
      "@container": "@set"
    },
    "hasModifications": {
      "@id": "roevo:hasModifications",
      "@type": "@id",
      "@container": "@set"
    },
    "archiveLocation": {
      "@id": "roevo:archiveLocation",
      "@type": "@id"
    },
    "@id": {
      "@context": {}
    },
    "roevo:hasVersion": {},
    "roevo:wasSnapshotOf": {},
    "roevo:wasArchivedFrom": {},
    "roevo:createdAtTime": {},
    "roevo:modifiedAtTime": {},
    "roevo:archivedAtTime": {},
    "roevo:hasChangeLog": {},
    "roevo:hasAdditions": {},
    "roevo:hasRemovals": {},
    "roevo:hasModifications": {},
    "ro": "http://purl.org/wf4ever/ro#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "ore": "http://www.openarchives.org/ore/terms/",
    "roevo": "http://purl.org/wf4ever/roevo#",
    "prov": "http://www.w3.org/ns/prov#",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roevo/context.jsonld)

## Sources

* [Research Object Evolution Ontology](http://purl.org/wf4ever/roevo)
* [PROV-O: The PROV Ontology](https://www.w3.org/TR/prov-o/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roevo`

