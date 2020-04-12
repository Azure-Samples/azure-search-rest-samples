# Postman collections for Azure Cognitive Search

This repository provides Postman collections used in REST API walkthroughs. All collections are saved in JSON, in the V2 collection format.

To use these collections, import them into **Postman**.

## Query examples: Full syntax, Patterns and special characters, Simple syntax

Query requests in these collections demonstrate syntax for a broad range of scenarios described in these articles: [Full Lucene syntax examples](https://docs.microsoft.com/azure/search/search-query-lucene-examples), [Partial term and pattern matching](https://docs.microsoft.com/azure/search/search-query-partial-matching), [Simple syntax query examples](https://docs.microsoft.com/azure/search/query-simple-syntax).

With the exception of Full Syntax, which queries the read-only NYCJobs index hosted in a sandbox service, you must edit a collection to replace placeholder values with an endpoint and API key that is valid for your service.

1. After importing the collection, expand the (`...`) action list and select **Edit**.

2. Enter the search service name and an admin API key. Admin access is required to create and delete objects on a search service. After saving your changes, you can run each query with no further modification.

Most examples are self-explanatory. For the NOT query, see the Boolean operator section for either [simple](https://docs.microsoft.com/azure/search/query-simple-syntax).

## Knowledge-store collection

Contains requests for creating and populating an index with hotel reviews data from Kaggle. The collection also includes an indexer and skillset that contains instructions for expressing a knowledge store in Azure Storage.

## Quickstart collection

Includes 4 requests used to create an index, load documents, search the index, and query system information. Request bodies include JSON documents that provides index and documents.  

## Tutorial collection

This collection provides the same requests as those used to build an AI enrichment pipeline in [Tutorial: Add structure to "unstructured content" using REST APIs](https://docs.microsoft.com/azure/search/cognitive-search-tutorial-blob). 