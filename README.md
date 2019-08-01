---
topic: sample
services: azure-search
platforms: rest
languages:
  - rest
name: Azure Search REST calls in Postman
description: |
  Postman collections containing REST API calls to Azure Search.
products:
  - azure
  - azure-search
urlFragment: rest-postman-collections
---

# Postman collections for Azure Search

This repository provides Postman collections used in Azure Search walkthroughs. All collections are saved in JSON, in the V2 collection format.

To use these collections, import them into **Postman**.

## AzureSearchQuickstart collection

Includes 4 requests used to create an index, load documents, search the index, and query system information. Request bodies include JSON documents that provides index and documents.  

## Caselaw collection

Includes 4 requests used to create an index, data source, skillset, and indexer using [Caselaw demo data](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/caselaw) from Azure Search Sample Data.

This collection is used in [How to get started with Knowledge Store](https://docs.microsoft.com/azure/search/knowledge-store-howto).
