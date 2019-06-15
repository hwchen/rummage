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

- how to handle synonyms?
