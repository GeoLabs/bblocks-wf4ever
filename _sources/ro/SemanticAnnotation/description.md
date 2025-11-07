# ro:SemanticAnnotation

## Description

A **SemanticAnnotation** is a specialization of `ao:Annotation` which requires that the annotation body (`ao:body`) points to an **RDF Graph**. This graph contains semantic information about the annotated resource, expressed using RDF triples.

This might be a Named Graph or a resource which can be resolved separately from the URI given by `ao:body`.

The RDF graph SHOULD mention the resources identified by `ao:annotatesResource`, preferably by using their URIs as subject or object of RDF statements.

## Properties

- `@id` : Unique identifier for the annotation
- `@type` : Must be SemanticAnnotation
- `body` : URI pointing to an RDF Graph containing semantic annotation content
- `annotatesResource` : The resource(s) that this annotation describes
- `created` : Creation date of the annotation
- `creator` : The agent who created this annotation

## Relations

- Annotates resources via `ao:annotatesResource`
- Has a semantic body (RDF Graph) via `ao:body`
- Subclass of `ao:Annotation` from the Annotation Ontology

## Difference from ao:hasTopic

Note that the use of `ao:body` in SemanticAnnotation is distinct from `ao:hasTopic`:
- **`ao:body`**: The RDF graph is the annotation content (it describes/mentions the annotated resource)
- **`ao:hasTopic`**: The RDF graph is the "topic" or "bookmark" of the annotated resource

For `ro:SemanticAnnotation`, the graph body merely needs to **mention** the annotated resource (e.g., to give it a `dc:title` or to relate it to other resources), without necessarily being its "topic".

## Use Cases

- Semantic metadata expressed in RDF (e.g., Dublin Core, FOAF, PROV-O)
- Linking resources using semantic relationships
- Provenance graphs describing resource creation
- Quality assessments with structured vocabularies

## Example

```json
{
  "@id": "#annotation-1",
  "@type": "SemanticAnnotation",
  "annotatesResource": "data/results.csv",
  "body": ".ro/annotations/metadata-1.ttl",
  "created": "2025-11-07T10:00:00Z",
  "creator": "https://orcid.org/0000-0002-1825-0097"
}
```

Where `metadata-1.ttl` contains RDF triples like:

```turtle
@prefix dc: <http://purl.org/dc/terms/> .
@prefix prov: <http://www.w3.org/ns/prov#> .

<data/results.csv> 
    dc:title "NDVI Analysis Results" ;
    dc:format "text/csv" ;
    prov:wasGeneratedBy <#workflow-run-123> .
```
