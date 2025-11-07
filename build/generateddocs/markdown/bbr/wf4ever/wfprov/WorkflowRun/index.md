
# wfprov:WorkflowRun (Schema)

`ogc.bbr.wf4ever.wfprov.WorkflowRun` *v1.0*

An execution instance of a workflow. A WorkflowRun is a special type of ProcessRun that represents the execution of a complete workflow (wfdesc:Workflow), containing multiple ProcessRuns for its sub-processes.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# wfprov:WorkflowRun

## Description

A **WorkflowRun** represents an execution instance of a complete workflow. It is a specialized type of ProcessRun that represents the execution of a `wfdesc:Workflow`, containing multiple ProcessRuns for its sub-processes.

## Class Hierarchy

Inherits all properties from `wfprov:ProcessRun`.

## Relations

- Extends `wfprov:ProcessRun`
- Must be linked to a `wfdesc:Workflow` via `describedByWorkflow`
- Contains `wfprov:ProcessRun` via `hadSubProcessRun`
- Can be executed by a `wfprov:WorkflowEngine` via `wasEnactedBy`

## Examples

### Simple workflow run
#### json
```json
{
  "@id": "#simple-workflow-run-1",
  "@type": "WorkflowRun",
  "describedByWorkflow": "#simple-workflow",
  "describedByProcess": "#simple-workflow",
  "startedAtTime": "2025-11-07T09:00:00Z",
  "endedAtTime": "2025-11-07T09:05:00Z",
  "hadSubProcessRun": [
    { "@id": "#process-run-1" }
  ],
  "wasEnactedBy": "#workflow-engine"
}

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/wfprov/WorkflowRun/context.jsonld",
  "@id": "#simple-workflow-run-1",
  "@type": "WorkflowRun",
  "describedByWorkflow": "#simple-workflow",
  "describedByProcess": "#simple-workflow",
  "startedAtTime": "2025-11-07T09:00:00Z",
  "endedAtTime": "2025-11-07T09:05:00Z",
  "hadSubProcessRun": [
    {
      "@id": "#process-run-1"
    }
  ],
  "wasEnactedBy": "#workflow-engine"
}
```

#### ttl
```ttl
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix wfprov: <http://purl.org/wf4ever/wfprov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<file:///github/workspace/#process-run-1> wfprov:wasPartOfWorkflowRun <file:///github/workspace/#simple-workflow-run-1> .

<file:///github/workspace/#simple-workflow-run-1> a wfprov:WorkflowRun ;
    wfprov:describedByProcess <file:///github/workspace/#simple-workflow> ;
    wfprov:describedByWorkflow <file:///github/workspace/#simple-workflow> ;
    prov:endedAtTime "2025-11-07T09:05:00+00:00"^^xsd:dateTime ;
    prov:startedAtTime "2025-11-07T09:00:00+00:00"^^xsd:dateTime ;
    prov:wasAssociatedWith <file:///github/workspace/#workflow-engine> .


```


### Complex workflow run with multiple processes
#### json
```json
{
  "@id": "#ndvi-workflow-run-1",
  "@type": "WorkflowRun",
  "describedByWorkflow": "#ndvi-workflow",
  "describedByProcess": "#ndvi-workflow",
  "usedInput": [
    { "@id": "artifact/landsat_scene.tif" }
  ],
  "startedAtTime": "2025-11-07T10:00:00Z",
  "endedAtTime": "2025-11-07T10:15:00Z",
  "hadSubProcessRun": [
    { "@id": "#extract-bands-run-1" },
    { "@id": "#ndvi-calc-run-1" },
    { "@id": "#reproject-run-1" }
  ],
  "wasEnactedBy": "#zoo-wps-engine"
}

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/wfprov/WorkflowRun/context.jsonld",
  "@id": "#ndvi-workflow-run-1",
  "@type": "WorkflowRun",
  "describedByWorkflow": "#ndvi-workflow",
  "describedByProcess": "#ndvi-workflow",
  "usedInput": [
    {
      "@id": "artifact/landsat_scene.tif"
    }
  ],
  "startedAtTime": "2025-11-07T10:00:00Z",
  "endedAtTime": "2025-11-07T10:15:00Z",
  "hadSubProcessRun": [
    {
      "@id": "#extract-bands-run-1"
    },
    {
      "@id": "#ndvi-calc-run-1"
    },
    {
      "@id": "#reproject-run-1"
    }
  ],
  "wasEnactedBy": "#zoo-wps-engine"
}
```

#### ttl
```ttl
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix wfprov: <http://purl.org/wf4ever/wfprov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<file:///github/workspace/#extract-bands-run-1> wfprov:wasPartOfWorkflowRun <file:///github/workspace/#ndvi-workflow-run-1> .

<file:///github/workspace/#ndvi-calc-run-1> wfprov:wasPartOfWorkflowRun <file:///github/workspace/#ndvi-workflow-run-1> .

<file:///github/workspace/#reproject-run-1> wfprov:wasPartOfWorkflowRun <file:///github/workspace/#ndvi-workflow-run-1> .

<file:///github/workspace/#ndvi-workflow-run-1> a wfprov:WorkflowRun ;
    wfprov:describedByProcess <file:///github/workspace/#ndvi-workflow> ;
    wfprov:describedByWorkflow <file:///github/workspace/#ndvi-workflow> ;
    wfprov:usedInput <file:///github/workspace/artifact/landsat_scene.tif> ;
    prov:endedAtTime "2025-11-07T10:15:00+00:00"^^xsd:dateTime ;
    prov:startedAtTime "2025-11-07T10:00:00+00:00"^^xsd:dateTime ;
    prov:wasAssociatedWith <file:///github/workspace/#zoo-wps-engine> .


```


### KindGrove Mangrove Analysis Execution
#### json
```json
{
  "@id": "urn:uuid:f02b8997-a6b1-4909-9946-9129c2b3f10c",
  "@type": "WorkflowRun",
  "label": "KindGrove Mangrove Analysis - Myanmar Region",
  "describedByWorkflow": "https://github.com/starling-foundries/KindGrove#mangrove-analysis",
  "describedByProcess": "https://github.com/starling-foundries/KindGrove#mangrove-analysis",
  "startedAtTime": "2025-11-03T15:14:02.032122",
  "endedAtTime": "2025-11-03T15:14:17.039961",
  "wasEnactedBy": "urn:uuid:5b925446-32a4-4104-9724-fa7360e1ef60",
  "usedInput": [
    { "@id": "urn:uuid:192e18cb-9182-4147-ad13-03076e7a3b3d" },
    { "@id": "urn:uuid:91b4ec49-d11a-4407-9685-032bf7e95258" },
    { "@id": "urn:uuid:ced76ef7-e660-4798-9442-06c17a45bbea" },
    { "@id": "urn:uuid:6daa697b-40e3-499b-ade7-b404d089febb" },
    { "@id": "urn:uuid:fd57ac88-8716-40ed-8945-f83914857523" },
    { "@id": "urn:uuid:5007bfea-1116-4751-96b1-ff453b3ce5e6" },
    { "@id": "urn:uuid:dc628f49-ccaa-479d-9a39-0eb1eb293d6b" }
  ],
  "hadSubProcessRun": [
    { "@id": "#subprocess-1" },
    { "@id": "#subprocess-2" }
  ]
}

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/wfprov/WorkflowRun/context.jsonld",
  "@id": "urn:uuid:f02b8997-a6b1-4909-9946-9129c2b3f10c",
  "@type": "WorkflowRun",
  "label": "KindGrove Mangrove Analysis - Myanmar Region",
  "describedByWorkflow": "https://github.com/starling-foundries/KindGrove#mangrove-analysis",
  "describedByProcess": "https://github.com/starling-foundries/KindGrove#mangrove-analysis",
  "startedAtTime": "2025-11-03T15:14:02.032122",
  "endedAtTime": "2025-11-03T15:14:17.039961",
  "wasEnactedBy": "urn:uuid:5b925446-32a4-4104-9724-fa7360e1ef60",
  "usedInput": [
    {
      "@id": "urn:uuid:192e18cb-9182-4147-ad13-03076e7a3b3d"
    },
    {
      "@id": "urn:uuid:91b4ec49-d11a-4407-9685-032bf7e95258"
    },
    {
      "@id": "urn:uuid:ced76ef7-e660-4798-9442-06c17a45bbea"
    },
    {
      "@id": "urn:uuid:6daa697b-40e3-499b-ade7-b404d089febb"
    },
    {
      "@id": "urn:uuid:fd57ac88-8716-40ed-8945-f83914857523"
    },
    {
      "@id": "urn:uuid:5007bfea-1116-4751-96b1-ff453b3ce5e6"
    },
    {
      "@id": "urn:uuid:dc628f49-ccaa-479d-9a39-0eb1eb293d6b"
    }
  ],
  "hadSubProcessRun": [
    {
      "@id": "#subprocess-1"
    },
    {
      "@id": "#subprocess-2"
    }
  ]
}
```

#### ttl
```ttl
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix wfprov: <http://purl.org/wf4ever/wfprov#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<file:///github/workspace/#subprocess-1> wfprov:wasPartOfWorkflowRun <urn:uuid:f02b8997-a6b1-4909-9946-9129c2b3f10c> .

<file:///github/workspace/#subprocess-2> wfprov:wasPartOfWorkflowRun <urn:uuid:f02b8997-a6b1-4909-9946-9129c2b3f10c> .

<urn:uuid:f02b8997-a6b1-4909-9946-9129c2b3f10c> a wfprov:WorkflowRun ;
    wfprov:describedByProcess <https://github.com/starling-foundries/KindGrove#mangrove-analysis> ;
    wfprov:describedByWorkflow <https://github.com/starling-foundries/KindGrove#mangrove-analysis> ;
    wfprov:label "KindGrove Mangrove Analysis - Myanmar Region" ;
    wfprov:usedInput <urn:uuid:192e18cb-9182-4147-ad13-03076e7a3b3d>,
        <urn:uuid:5007bfea-1116-4751-96b1-ff453b3ce5e6>,
        <urn:uuid:6daa697b-40e3-499b-ade7-b404d089febb>,
        <urn:uuid:91b4ec49-d11a-4407-9685-032bf7e95258>,
        <urn:uuid:ced76ef7-e660-4798-9442-06c17a45bbea>,
        <urn:uuid:dc628f49-ccaa-479d-9a39-0eb1eb293d6b>,
        <urn:uuid:fd57ac88-8716-40ed-8945-f83914857523> ;
    prov:endedAtTime "2025-11-03T15:14:17.039961"^^xsd:dateTime ;
    prov:startedAtTime "2025-11-03T15:14:02.032122"^^xsd:dateTime ;
    prov:wasAssociatedWith <urn:uuid:5b925446-32a4-4104-9724-fa7360e1ef60> .


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: An execution instance of a workflow
allOf:
- $ref: https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/wfprov/ProcessRun/schema.yaml
- type: object
  properties:
    '@type':
      const: WorkflowRun
    describedByWorkflow:
      type: string
      format: uri
      description: Links to the workflow description (wfdesc:Workflow) that was executed
      x-jsonld-id: http://purl.org/wf4ever/wfprov#describedByWorkflow
      x-jsonld-type: '@id'
    hadSubProcessRun:
      type: array
      items:
        type: object
        properties:
          '@id':
            type: string
            format: uri
        required:
        - '@id'
      description: The process runs that were part of this workflow execution
      x-jsonld-reverse: wfprov:wasPartOfWorkflowRun
      x-jsonld-type: '@id'
      x-jsonld-container: '@set'
    wasEnactedBy:
      type: string
      format: uri
      description: The workflow engine that executed this workflow
      x-jsonld-id: http://www.w3.org/ns/prov#wasAssociatedWith
      x-jsonld-type: '@id'
x-jsonld-extra-terms:
  WorkflowRun: http://purl.org/wf4ever/wfprov#WorkflowRun
x-jsonld-vocab: http://purl.org/wf4ever/wfprov#
x-jsonld-prefixes:
  wfprov: http://purl.org/wf4ever/wfprov#
  prov: http://www.w3.org/ns/prov#
  wfdesc: http://purl.org/wf4ever/wfdesc#

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/wfprov/WorkflowRun/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/wfprov/WorkflowRun/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@vocab": "http://purl.org/wf4ever/wfprov#",
    "ProcessRun": "wfprov:ProcessRun",
    "WorkflowRun": "wfprov:WorkflowRun",
    "wasOutputFrom": {
      "@id": "prov:generated",
      "@type": "@id",
      "@container": "@set"
    },
    "describedByProcess": {
      "@id": "wfprov:describedByProcess",
      "@type": "@id"
    },
    "usedInput": {
      "@id": "wfprov:usedInput",
      "@type": "@id",
      "@container": "@set"
    },
    "startedAtTime": {
      "@id": "prov:startedAtTime",
      "@type": "http://www.w3.org/2001/XMLSchema#dateTime"
    },
    "endedAtTime": {
      "@id": "prov:endedAtTime",
      "@type": "http://www.w3.org/2001/XMLSchema#dateTime"
    },
    "wasPartOfWorkflowRun": {
      "@id": "wfprov:wasPartOfWorkflowRun",
      "@type": "@id"
    },
    "describedByWorkflow": {
      "@id": "wfprov:describedByWorkflow",
      "@type": "@id"
    },
    "hadSubProcessRun": {
      "@reverse": "wfprov:wasPartOfWorkflowRun",
      "@type": "@id",
      "@container": "@set"
    },
    "wasEnactedBy": {
      "@id": "prov:wasAssociatedWith",
      "@type": "@id"
    },
    "wfprov": "http://purl.org/wf4ever/wfprov#",
    "prov": "http://www.w3.org/ns/prov#",
    "wfdesc": "http://purl.org/wf4ever/wfdesc#",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/wfprov/WorkflowRun/context.jsonld)

## Sources

* [Workflow Provenance Ontology - WorkflowRun](http://purl.org/wf4ever/wfprov#WorkflowRun)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/wfprov/WorkflowRun`

