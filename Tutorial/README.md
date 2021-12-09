---
page_type: sample
languages:
  - rest
name: Skillset Tutorial in REST - Postman
description: |
  Create an AI enrichment pipeline in Azure Cognitive Search to extract information and structure from Azure blobs.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-tutorial
---

# Create a skillset in Azure Cognitive Search using REST APIs and Postman

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

Demonstrates using Postman and the Azure Cognitive Search REST APIs to send requests that create a data source, a skillset, index, and indexer. Requests are provided in the V2.1 collection format, which you can import and then modify for connections to your search service and Azure Storage.

Skillset steps include OCR, language detection, entity recognition, and key phrase extraction. The sample demo files consist of multiple content types ranging from image-only, text-only, and rich application files with embedded images and text. The end result is searchable index that you can query for new and enriched content.

This collection is featured in the [Tutorial: Use REST and AI to generate searchable content from Azure blobs](https://docs.microsoft.com/azure/search/cognitive-search-tutorial-blob). If you have trouble with the steps in this readme, check the tutorial for more detailed instructions.

## Contents

| File/folder | Description |
|-------------|-------------|
| `cog-search-demo REST tutorial.postman_collection.json`       | Import into Postman |
| `.gitignore` | Define what to ignore at commit time. |
| `CONTRIBUTING.md` | Guidelines for contributing to the sample. |
| `README.md` | This README file. |
| `LICENSE`   | The license for the sample. |

## Prerequisites

- [Postman Desktop app](https://www.getpostman.com/)
- [Azure Cognitive Search service](https://docs.microsoft.com/azure/search/search-create-service-portal)
- [Azure Storage](https://docs.microsoft.com/azure/storage/common/storage-account-create)
- [Sample data files](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/ai-enrichment-mixed-media)

## Setup

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.
1. Create or find your search service.
1. Get the search service admin API key.
1. Create an Azure Storage resource of kind StorageV2 (general purpose v2).
1. Create a blob container and upload the sample data files from the azure-search-sample-data GitHub repository.
1. Get the connection string to Azure Storage.

### Run the sample

1. Start Postman and import cog-search-demo REST tutorial.postman_collection.json
1. Modify the collection variables to specify your search service, admin key, storage service, and blob container.
1. Send each request to the service to create a data source, index, skillset, and indexer.
1. Wait for the indexer to process. It will take several minutes to complete.
1. Run queries to return the enriched content.

## Next steps

You can learn more about Azure Cognitive Search on the [official documentation site](https://docs.microsoft.com/azure/search).