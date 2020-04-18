---
page_type: sample
languages:
  - rest
name: Create projections using REST - Postman
description: |
  Azure Cognitive Search supports the creation of a knowledge store to contain AI-generated content, inferred from image and text analysis over raw content files. Projections are the physical expressions of your data. In this collection, work with examples that create table, object, and file projections.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-knowledge-store-tutorial
---

#  Creating projections in Azure Cognitive Search using REST APIs and Postman

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

This [Postman](https://www.getpostman.com/) collection uses the Azure Cognitive Search REST APIs to create the resources associated with a knowledge store projection: a data source, a skillset, an index, and an indexer. Requests are provided in the V2 collection format, which you can import and then modify for connections to your search service.

The knowledge store and index configuration are based on the source document being PDFs or documents with text and images. This is discussed in the tutorial [Knowledge store projections: How to shape and export enrichments to the knowledge store](https://docs.microsoft.com/azure/search/knowledge-store-projections-examples).

The purpose of this sample is to demonstrate how you use table, object and file projections effectively to project your enriched documents to the knowledge store. 

## Contents

| File/folder | Description |
|-------------|-------------|
| `projections.postman_collection.json`       | Import into Postman |
| `CONTRIBUTING.md` | Guidelines for contributing to the sample. |
| `README.md` | This README file. |
| `LICENSE.md`   | The license for the sample. |

## Prerequisites

- [Postman Desktop app](https://www.getpostman.com/)
- [Azure Cognitive Search service](https://docs.microsoft.com/azure/search/search-create-service-portal)

## Setup

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.

### Set environment variables

1. Create a container in Azure Storage with a few PDFs or other documents.
1. Start Postman and import KnowledgeStore.postman_collection.json
1. In the collection, open the **Edit** dialog and the **Variables** tab
1. Set `admin-key`. You'll find the value for `admin-key` in the Search Service's **Keys** tab. 
1. Set `search-service-name` and `storage-account-name`. These must be set to the name of your search service and the name of the storage account at which you've stored the source document .
1. Set `storage-connection-string` to the value in the Storage Account's **Access Keys** tab. 
1. Set `datasource-container` to the name of the container you uploaded your documents to
1. Set `cognitive-services-key` to the Cognitive Services key

### Running tutorial

1. Execute the create datasource request
1. Execute the create index request
1. Execute the create skillset request
1. Execute the create indexer request
1. Validate your results by running the indexer
1. Execute the 01 update skillset request
1. Run the indexer and validate that the table projections are created
1. Execute the 02 update skillset request
1. Run the indexer and validate that the object projections are created
1. Execute the 03 update skillset request
1. Run the indexer and validate that the file projections are created
1. Execute the 04 update skillset request
1. Run the indexer and validate that the table, object and file projections are created and related

## Next steps

You can learn more about Azure Cognitive Search on the [official documentation site](https://docs.microsoft.com/azure/search).
