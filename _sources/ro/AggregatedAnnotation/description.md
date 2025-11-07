# ro:AggregatedAnnotation

## Description

An **AggregatedAnnotation** is an annotation about resources within a Research Object. It is a specialization of `ro:SemanticAnnotation` that is specifically aggregated within an `ro:ResearchObject`.

As a subclass of `ro:SemanticAnnotation`, the annotation body must point to an RDF Graph which contains the actual semantic annotation. Annotations provide additional metadata, provenance information, or contextual details about aggregated resources, stored as part of the Research Object itself.

## Properties

- `@id` : Unique identifier for the annotation
- `@type` : Must be AggregatedAnnotation
- `annotatesAggregatedResource` : The resource(s) that this annotation describes
- `body` : The body of the annotation (typically a URI to an annotation document)
- `created` : Creation date of the annotation

## Relations

- Annotates one or more `ro:Resource` via `ro:annotatesAggregatedResource`
- Has an annotation body via `oa:hasBody`
- Aggregated in a `ro:ResearchObject`

## Use Cases

- Provenance metadata about a data file
- Quality description of a result
- License and attribution for a resource
- Research notes and observations

## Example

```json
{
  "@id": ".ro/annotations/annotation-1.json",
  "@type": "AggregatedAnnotation",
  "annotatesAggregatedResource": "data/landsat_scene.tif",
  "body": ".ro/annotations/body-1.ttl",
  "created": "2025-11-07T10:00:00Z"
}
```
