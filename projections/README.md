---
page_type: sample
languages:
  - rest
name: Create projections using REST - Postman
description: |
  Use projections to determine the physical expression of your AI-generated content in an Azure Cognitive Search knowledge store. 
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-knowledge-store-projections
---

# Creating projections in Azure Cognitive Search using REST APIs and Postman

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

This [Postman](https://www.getpostman.com/) collection uses the Azure Cognitive Search REST APIs to create the resources associated with a knowledge store projection: a data source, a skillset, an index, and an indexer. Requests are provided in the V2.1 collection format, which you can import and then modify for connections to your search service.

The skillset, knowledge store projections, and index schema accommodate source documents that include both text and image content. See [Detailed example of shapes and projections in a knowledge store](https://docs.microsoft.com/azure/search/knowledge-store-projections-example-long) for more information about the projections and shapes in this collection.

The purpose of this sample is to demonstrate how you use table, object and file projections effectively to project your enriched documents to the knowledge store. 

## Contents

| File/folder | Description |
|-------------|-------------|
| `Projections Docs.postman_collection.json`       | Import into Postman |
| `CONTRIBUTING.md` | Guidelines for contributing to the sample. |
| `README.md` | This README file. |
| `LICENSE.md`   | The license for the sample. |

## Prerequisites

+ [Postman Desktop app](https://www.getpostman.com/)
+ [Azure Cognitive Search](https://docs.microsoft.com/azure/search/search-create-service-portal)
+ [Azure Storage](https://docs.microsoft.com/en-us/azure/storage/)
+ [Azure Cognitive Services multi-service resource](https://docs.microsoft.com/azure/cognitive-services/cognitive-services-apis-create-account?tabs=multiservice%2Clinux) 
+ [Sample data (mixed content types)](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/ai-enrichment-mixed-media), uploaded to a container in Azure Storage

## Setup

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.

### Set environment variables

1. Start Postman Desktop app and import "Projections Docs.postman_collection.json".
1. In the collection, right-click the collection name, select **Edit**, and then select **Variables**.
1. Set `search-service-name` and `storage-account-name` to the names of your search service, and to the storage account at which you've stored the sample data.
1. Set `admin-key`. You'll find the value for `admin-key` in the Search Service's **Keys** tab. 
1. Set `storage-connection-string` to the value in the Storage Account's **Access Keys** tab. 
1. Set `datasource-container` to the name of the container you uploaded your documents to.
1. Set `cognitive-services-key` to a multi-service Cognitive Services key.

### Send requests

After the environment variables are set, send each request in sequence to create resources in your search service and a knowledge store in Azure Storage.

The first set creates the data source, index, skillset, and indexer. There is no knowledge store at this point.

1. Send the create data source request.
1. Send the create index request.
1. Send the create skillset request.
1. Send the create indexer request.
1. Check the search service pages in the Azure portal to verify each resource is created in Azure Cognitive Search. 

Wait for the indexer to finish processing before continuing to the next step.

Next, send a request that adds a Shaper skill and updates the "knowledgeStore" section of the skillset with table projections. Then, run the indexer to invoke skillset execution, creating a knowledge store table in Azure Storage.

1. Execute the 01 update skillset request
1. Run the indexer request to process the changes.
1. Use the Azure portal to connect to Azure Storage, and then use Storage browser to view the tables.

For each additional skillset update, send the request, run the indexer, and check the results using Storage browser.

+ Execute the 02 update skillset request to create json objects, one for each source document.
+ Execute the 03 update skillset request to create binary objects, one for each image file only.
+ Execute the 04 update skillset request to create a second set of projections that cross all object types (tables, objects, images).

The last set of projections demonstrates projections that use the same shapes in multiple physical expressions.

## Next steps

You can learn more about Azure Cognitive Search on the [official documentation site](https://docs.microsoft.com/azure/search).
