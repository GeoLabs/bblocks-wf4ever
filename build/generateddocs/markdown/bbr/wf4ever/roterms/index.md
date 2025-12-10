
# Research Object Terms (roterms) (Schema)

`ogc.bbr.wf4ever.roterms` *v1.0*

The Research Object Terms vocabulary defines classes and properties for annotations on Research Objects and their resources.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

# Research Object Terms (roterms)

## Overview

The Research Object Terms vocabulary (`roterms`) defines classes and properties that may be used with annotations on Research Objects and their resources. It provides a rich vocabulary for describing scientific concepts, tasks, hypotheses, and quality metrics.

## Namespace

`http://purl.org/wf4ever/roterms#`

## Key Classes

### Scientific Concepts

- **Hypothesis** - A scientific hypothesis being tested or explored
- **Conclusion** - A conclusion drawn from research
- **ExperimentalDesign** - Description of experimental methodology
- **ScientificMethod** - A specific scientific method or approach

### Resource Types

- **Sketch** - A sketch or preliminary design
- **Note** - A research note or annotation
- **ProspectivePlan** - A plan for future research
- **Software** - Software or code artifact
- **WebService** - A web service used in research

### Quality and Review

- **QualityAnnotation** - Annotation about quality aspects
- **Review** - A peer review or assessment
- **Rating** - A quality rating

## Key Properties

### Descriptive Properties

- **exampleValue** - Provides an example value for a parameter or input
  - Domain: Any resource
  - Range: Literal or Resource
  - Usage: Document expected input formats

- **defaultValue** - Specifies a default value
  - Domain: Parameter or Input
  - Range: Literal or Resource

- **sampleSize** - Sample size for statistical analysis
  - Domain: Dataset or Analysis
  - Range: Integer

### Functional Properties

- **performsTask** - Describes the task performed by a process or workflow
  - Domain: Process, Workflow, or Software
  - Range: Task or Literal description
  - Usage: Semantic description of functionality

- **requiresHardware** - Hardware requirements for execution
  - Domain: Software or Process
  - Range: Hardware specification

- **requiresSoftware** - Software dependencies
  - Domain: Software or Workflow
  - Range: Software package

### Provenance Properties

- **wasInputTo** - Resource was input to a process
  - Domain: Resource or Artifact
  - Range: Process or Activity

- **wasOutputFrom** - Resource was output from a process
  - Domain: Resource or Artifact
  - Range: Process or Activity

- **authoredBy** - Created by a specific person or agent
  - Domain: Any resource
  - Range: Agent (Person or Organization)

- **authoredOn** - Date/time of authoring
  - Domain: Any resource
  - Range: DateTime

### Scientific Properties

- **hypothesis** - Links to a hypothesis being tested
  - Domain: Experiment or Research Object
  - Range: Hypothesis

- **supports** - Evidence that supports a claim or hypothesis
  - Domain: Artifact or Result
  - Range: Hypothesis or Claim

- **refutes** - Evidence that refutes a claim or hypothesis
  - Domain: Artifact or Result
  - Range: Hypothesis or Claim

- **methodology** - Research methodology employed
  - Domain: Research Object or Experiment
  - Range: ScientificMethod or ExperimentalDesign

### Quality Properties

- **technicalStandard** - Technical standard conformed to
  - Domain: Resource
  - Range: Standard specification

- **validatedBy** - Validation process or tool used
  - Domain: Resource or Artifact
  - Range: Validation method

- **qualityScore** - Numerical quality score
  - Domain: Any resource
  - Range: Float (0-1 or 0-100)

## Usage Examples

### Example Values for Parameters

```json
{
  "@context": "http://purl.org/wf4ever/roterms",
  "@type": "wfdesc:Input",
  "name": "threshold",
  "roterms:exampleValue": 0.95,
  "roterms:defaultValue": 0.8,
  "description": "Confidence threshold for classification"
}
```

### Task Description

```json
{
  "@context": "http://purl.org/wf4ever/roterms",
  "@type": "wfdesc:Process",
  "name": "ImageClassifier",
  "roterms:performsTask": {
    "@type": "roterms:Task",
    "label": "Image Classification",
    "description": "Classifies images using deep learning"
  },
  "roterms:requiresSoftware": "TensorFlow 2.0+"
}
```

### Hypothesis Testing

```json
{
  "@context": "http://purl.org/wf4ever/roterms",
  "@type": "ro:ResearchObject",
  "roterms:hypothesis": {
    "@type": "roterms:Hypothesis",
    "description": "Higher temperature increases reaction rate",
    "@id": "urn:uuid:hypothesis-001"
  },
  "aggregates": [
    {
      "@id": "results.csv",
      "@type": "wf4ever:Dataset",
      "roterms:supports": "urn:uuid:hypothesis-001"
    }
  ]
}
```

### Quality Annotation

```json
{
  "@context": "http://purl.org/wf4ever/roterms",
  "@type": "roterms:QualityAnnotation",
  "annotates": "workflow.cwl",
  "roterms:qualityScore": 0.87,
  "roterms:validatedBy": "CWL Validator 1.2",
  "roterms:technicalStandard": "CWL v1.2"
}
```

## Integration with Other Vocabularies

### Dublin Core Terms

roterms complements Dublin Core with research-specific terms:

- Use `dcterms:creator` for general authorship
- Use `roterms:authoredBy` for explicit research authorship with provenance

### PROV-O

roterms extends PROV-O provenance:

- `roterms:wasInputTo` / `roterms:wasOutputFrom` complement PROV relationships
- Provides domain-specific provenance for scientific workflows

### Schema.org

roterms can be used alongside schema.org vocabulary for better web discoverability.

## Use Cases

### Documentation

Provide comprehensive documentation of workflow parameters with examples and defaults.

### Reproducibility

Document exact software versions, hardware requirements, and methodology for reproducible research.

### Quality Assurance

Track validation results, quality scores, and conformance to standards.

### Scientific Communication

Explicitly link research objects to hypotheses, conclusions, and scientific methods.

### Semantic Search

Enable semantic queries like "find all workflows that perform image classification" using `roterms:performsTask`.

## Best Practices

1. **Use exampleValue liberally** - Help users understand expected inputs
2. **Document dependencies** - Always specify software/hardware requirements
3. **Link to hypotheses** - Make scientific reasoning explicit
4. **Include quality metrics** - Document validation and quality scores
5. **Be specific with tasks** - Use controlled vocabularies for task descriptions

## References

- [Research Object Ontology](http://purl.org/wf4ever/ro)
- [Wf4Ever Research Object Model](http://wf4ever.github.io/ro/)
- [PROV-O](https://www.w3.org/TR/prov-o/)
- [Dublin Core Metadata Terms](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/)

## Examples

### Workflow Parameter with Example Value
#### json
```json
{
  "@context": "https://ogcincubator.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/context.jsonld",
  "@id": "threshold-param",
  "@type": "wfdesc:Input",
  "dcterms:title": "Confidence Threshold",
  "dcterms:description": "Minimum confidence level for classification",
  "roterms:exampleValue": 0.95,
  "roterms:defaultValue": 0.8
}

```


### Process with Task Description
#### json
```json
{
  "@context": "https://ogcincubator.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/context.jsonld",
  "@id": "image-classifier",
  "@type": "wfdesc:Process",
  "dcterms:title": "Image Classifier",
  "roterms:performsTask": {
    "@type": "roterms:Task",
    "label": "Image Classification",
    "description": "Classifies images using deep learning model"
  },
  "roterms:requiresSoftware": [
    "TensorFlow 2.0+",
    "Python 3.8+"
  ],
  "roterms:requiresHardware": "GPU with 8GB VRAM minimum"
}

```


### Research Object with Hypothesis
#### json
```json
{
  "@context": "https://ogcincubator.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/context.jsonld",
  "@id": "experiment-001",
  "@type": "ro:ResearchObject",
  "dcterms:title": "Temperature Effect on Reaction Rate",
  "roterms:hypothesis": {
    "@id": "hypothesis-001",
    "@type": "roterms:Hypothesis",
    "description": "Higher temperature increases chemical reaction rate exponentially"
  },
  "roterms:methodology": "Controlled laboratory experiment with varying temperature",
  "aggregates": [
    {
      "@id": "results.csv",
      "@type": "wf4ever:Dataset",
      "roterms:supports": "hypothesis-001",
      "roterms:sampleSize": 100
    }
  ]
}

```


### Quality Annotation
#### json
```json
{
  "@context": "https://ogcincubator.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/context.jsonld",
  "@id": "quality-annotation-001",
  "@type": "roterms:QualityAnnotation",
  "annotates": "workflow.cwl",
  "roterms:qualityScore": 0.87,
  "roterms:validatedBy": "CWL Validator 1.2",
  "roterms:technicalStandard": "CWL v1.2 Specification",
  "dcterms:created": "2025-11-28T10:00:00Z"
}

```


### Software Resource with Dependencies
#### json
```json
{
  "@context": "https://ogcincubator.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/context.jsonld",
  "@id": "analysis-tool",
  "@type": "roterms:Software",
  "dcterms:title": "Genomic Analysis Tool",
  "dcterms:version": "2.1.0",
  "roterms:requiresSoftware": [
    "R >= 4.0",
    "Bioconductor >= 3.12"
  ],
  "roterms:performsTask": "Gene expression analysis",
  "roterms:authoredBy": {
    "@type": "foaf:Person",
    "foaf:name": "Dr. Alice Johnson"
  },
  "roterms:authoredOn": "2025-06-15T00:00:00Z"
}

```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$id: http://purl.org/wf4ever/roterms
title: Research Object Terms
description: Schema for Research Object Terms vocabulary providing annotation properties
type: object
properties:
  '@type':
    oneOf:
    - type: string
      enum:
      - roterms:Hypothesis
      - roterms:Conclusion
      - roterms:ExperimentalDesign
      - roterms:ScientificMethod
      - roterms:Sketch
      - roterms:Note
      - roterms:ProspectivePlan
      - roterms:Software
      - roterms:WebService
      - roterms:QualityAnnotation
      - roterms:Review
      - roterms:Rating
      - roterms:Task
    - type: array
      items:
        type: string
  roterms:exampleValue:
    description: Example value for a parameter or input
  roterms:defaultValue:
    description: Default value for a parameter
  roterms:sampleSize:
    description: Sample size for statistical analysis
    type: integer
    minimum: 0
  roterms:performsTask:
    description: Task performed by a process or workflow
    oneOf:
    - type: string
    - type: object
      properties:
        '@type':
          const: roterms:Task
        label:
          type: string
        description:
          type: string
  roterms:requiresHardware:
    description: Hardware requirements for execution
    type: string
  roterms:requiresSoftware:
    description: Software dependencies
    oneOf:
    - type: string
    - type: array
      items:
        type: string
  roterms:wasInputTo:
    description: Process this resource was input to
    $ref: '#/$defs/ResourceReference'
  roterms:wasOutputFrom:
    description: Process this resource was output from
    $ref: '#/$defs/ResourceReference'
  roterms:authoredBy:
    description: Author of this resource
    $ref: '#/$defs/AgentReference'
  roterms:authoredOn:
    description: Date/time of authoring
    type: string
    format: date-time
  roterms:hypothesis:
    description: Hypothesis being tested
    oneOf:
    - $ref: '#/$defs/ResourceReference'
    - type: object
      properties:
        '@type':
          const: roterms:Hypothesis
        description:
          type: string
      required:
      - description
  roterms:supports:
    description: Hypothesis or claim this evidence supports
    $ref: '#/$defs/ResourceReference'
  roterms:refutes:
    description: Hypothesis or claim this evidence refutes
    $ref: '#/$defs/ResourceReference'
  roterms:methodology:
    description: Research methodology employed
    type: string
  roterms:technicalStandard:
    description: Technical standard conformed to
    type: string
  roterms:validatedBy:
    description: Validation process or tool used
    type: string
  roterms:qualityScore:
    description: Numerical quality score
    type: number
    minimum: 0
    maximum: 1
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
  AgentReference:
    oneOf:
    - type: string
    - type: object
      properties:
        '@type':
          enum:
          - foaf:Person
          - foaf:Organization
          - prov:Agent
        name:
          type: string
x-jsonld-extra-terms:
  Hypothesis: http://purl.org/wf4ever/roterms#Hypothesis
  Conclusion: http://purl.org/wf4ever/roterms#Conclusion
  ExperimentalDesign: http://purl.org/wf4ever/roterms#ExperimentalDesign
  ScientificMethod: http://purl.org/wf4ever/roterms#ScientificMethod
  Sketch: http://purl.org/wf4ever/roterms#Sketch
  Note: http://purl.org/wf4ever/roterms#Note
  ProspectivePlan: http://purl.org/wf4ever/roterms#ProspectivePlan
  Software: http://purl.org/wf4ever/roterms#Software
  WebService: http://purl.org/wf4ever/roterms#WebService
  QualityAnnotation: http://purl.org/wf4ever/roterms#QualityAnnotation
  Review: http://purl.org/wf4ever/roterms#Review
  Rating: http://purl.org/wf4ever/roterms#Rating
  Task: http://purl.org/wf4ever/roterms#Task
  exampleValue: http://purl.org/wf4ever/roterms#exampleValue
  defaultValue: http://purl.org/wf4ever/roterms#defaultValue
  sampleSize:
    x-jsonld-id: http://purl.org/wf4ever/roterms#sampleSize
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#integer
  performsTask:
    x-jsonld-id: http://purl.org/wf4ever/roterms#performsTask
    x-jsonld-type: '@id'
  requiresHardware: http://purl.org/wf4ever/roterms#requiresHardware
  requiresSoftware:
    x-jsonld-id: http://purl.org/wf4ever/roterms#requiresSoftware
    x-jsonld-container: '@set'
  wasInputTo:
    x-jsonld-id: http://purl.org/wf4ever/roterms#wasInputTo
    x-jsonld-type: '@id'
  wasOutputFrom:
    x-jsonld-id: http://purl.org/wf4ever/roterms#wasOutputFrom
    x-jsonld-type: '@id'
  authoredBy:
    x-jsonld-id: http://purl.org/wf4ever/roterms#authoredBy
    x-jsonld-type: '@id'
  authoredOn:
    x-jsonld-id: http://purl.org/wf4ever/roterms#authoredOn
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#dateTime
  hypothesis:
    x-jsonld-id: http://purl.org/wf4ever/roterms#hypothesis
    x-jsonld-type: '@id'
  supports:
    x-jsonld-id: http://purl.org/wf4ever/roterms#supports
    x-jsonld-type: '@id'
  refutes:
    x-jsonld-id: http://purl.org/wf4ever/roterms#refutes
    x-jsonld-type: '@id'
  methodology: http://purl.org/wf4ever/roterms#methodology
  technicalStandard: http://purl.org/wf4ever/roterms#technicalStandard
  validatedBy: http://purl.org/wf4ever/roterms#validatedBy
  qualityScore:
    x-jsonld-id: http://purl.org/wf4ever/roterms#qualityScore
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#float
x-jsonld-prefixes:
  roterms: http://purl.org/wf4ever/roterms#
  xsd: http://www.w3.org/2001/XMLSchema#
  ro: http://purl.org/wf4ever/ro#
  wfdesc: http://purl.org/wf4ever/wfdesc#
  prov: http://www.w3.org/ns/prov#
  foaf: http://xmlns.com/foaf/0.1/
  dcterms: http://purl.org/dc/terms/

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "Hypothesis": "roterms:Hypothesis",
    "Conclusion": "roterms:Conclusion",
    "ExperimentalDesign": "roterms:ExperimentalDesign",
    "ScientificMethod": "roterms:ScientificMethod",
    "Sketch": "roterms:Sketch",
    "Note": "roterms:Note",
    "ProspectivePlan": "roterms:ProspectivePlan",
    "Software": "roterms:Software",
    "WebService": "roterms:WebService",
    "QualityAnnotation": "roterms:QualityAnnotation",
    "Review": "roterms:Review",
    "Rating": "roterms:Rating",
    "Task": "roterms:Task",
    "exampleValue": "roterms:exampleValue",
    "defaultValue": "roterms:defaultValue",
    "sampleSize": {
      "@id": "roterms:sampleSize",
      "@type": "xsd:integer"
    },
    "performsTask": {
      "@id": "roterms:performsTask",
      "@type": "@id"
    },
    "requiresHardware": "roterms:requiresHardware",
    "requiresSoftware": {
      "@id": "roterms:requiresSoftware",
      "@container": "@set"
    },
    "wasInputTo": {
      "@id": "roterms:wasInputTo",
      "@type": "@id"
    },
    "wasOutputFrom": {
      "@id": "roterms:wasOutputFrom",
      "@type": "@id"
    },
    "authoredBy": {
      "@id": "roterms:authoredBy",
      "@type": "@id"
    },
    "authoredOn": {
      "@id": "roterms:authoredOn",
      "@type": "xsd:dateTime"
    },
    "hypothesis": {
      "@id": "roterms:hypothesis",
      "@type": "@id"
    },
    "supports": {
      "@id": "roterms:supports",
      "@type": "@id"
    },
    "refutes": {
      "@id": "roterms:refutes",
      "@type": "@id"
    },
    "methodology": "roterms:methodology",
    "technicalStandard": "roterms:technicalStandard",
    "validatedBy": "roterms:validatedBy",
    "qualityScore": {
      "@id": "roterms:qualityScore",
      "@type": "xsd:float"
    },
    "@type": {
      "@context": {}
    },
    "roterms:exampleValue": {},
    "roterms:defaultValue": {},
    "roterms:sampleSize": {},
    "label": {},
    "description": {},
    "roterms:performsTask": {},
    "roterms:requiresHardware": {},
    "roterms:requiresSoftware": {},
    "@id": {
      "@context": {}
    },
    "roterms:wasInputTo": {},
    "roterms:wasOutputFrom": {},
    "name": {},
    "roterms:authoredBy": {},
    "roterms:authoredOn": {},
    "roterms:hypothesis": {},
    "roterms:supports": {},
    "roterms:refutes": {},
    "roterms:methodology": {},
    "roterms:technicalStandard": {},
    "roterms:validatedBy": {},
    "roterms:qualityScore": {},
    "roterms": "http://purl.org/wf4ever/roterms#",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "ro": "http://purl.org/wf4ever/ro#",
    "wfdesc": "http://purl.org/wf4ever/wfdesc#",
    "prov": "http://www.w3.org/ns/prov#",
    "foaf": "http://xmlns.com/foaf/0.1/",
    "dcterms": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-wf4ever/build/annotated/bbr/wf4ever/roterms/context.jsonld)

## Sources

* [Research Object Terms](http://purl.org/wf4ever/roterms)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-wf4ever](https://github.com/GeoLabs/bblocks-wf4ever)
* Path: `_sources/roterms`

