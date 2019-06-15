# Rummage Architecture

## Modules list

- server: using actix (or maybe just hyper)
- core: traits and data structure for core engine. Built on tantivy?
- configuration: parsing and holding configuration options
- ingestion: methods for ingesting data and metadata and establishing relationships
- scoring: method for applying weights and scoring to search results
- query::nlp: methods for parsing natural language queries
- query::keyword: methods for parsing keyword queries
- geospatial

## Unknown

- how to handle synonyms? Maybe as query submodule. This could be a map, or perhaps some kind of ml model.

## Flow

### query processing
- server receives a query string.
- query string gets parsed (keyword or natural language)
- parsed query gets normal terms and context terms extracted. (A context term is something like counties. 'Maryland counties' should return a list of counties in maryland)
- each term may be a synonym of an existing indexed term. So "normalize" original term to indexed term.
- Query data structure is filled with all this pre-processed search and context

### searching index
... for now, tantivy?

### return results
- documents run through scoring pipeline.
- weight special factors, facet, etc.
- serialize results, confidence, etc.

