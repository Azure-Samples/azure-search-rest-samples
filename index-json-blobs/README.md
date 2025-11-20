---
page_type: sample
languages:
  - rest
name: Index nested JSON in REST
description: |
  Create an indexer in Azure AI Search that indexes nested JSON in a JSON array.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-json-indexer-tutorial
---

# Create an indexer in Azure AI Search that indexes nested JSON using REST APIs

This sample uses the Azure AI Search REST APIs to create an indexer, data source, and index for nested JSON within a JSON array. This example demonstrates the `jsonArray` parsing model and `documentRoot` parameters.

This sample is featured in [Tutorial: Index nested JSON blobs from Azure Storage using REST](https://learn.microsoft.com/azure/search/search-semi-structured-data).

## Prerequisites

+ An [Azure AI Search service](https://learn.microsoft.com/azure/search/search-create-service-portal) on any pricing tier.

+ An [Azure Storage account](https://learn.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal).

+ [Visual Studio Code](https://code.visualstudio.com/download) with the [REST Client extension](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

## Set up the data

1. Download the [sample data file](https://github.com/Azure-Samples/azure-search-sample-data/tree/main/ny-philharmonic/ny-philharmonic-free). Sample data is a single JSON file that contains a JSON array and 1,521 nested JSON elements.

1. In the Azure portal, [create a blob container](https://learn.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal) and upload the sample data file.

1. Make a note of the blob container name.

## Get connection information

Gather connection information used on the requests. You can find this information in the Azure portal. Save it in Notepad or another temporary location.

1. In Azure Storage, select **Security + networking** > **Access keys** from the left pane and copy a connection string. It should be in this format: `DefaultEndpointsProtocol=https;AccountName=<YOUR-STORAGE-ACCOUNT>;AccountKey=<YOUR-ACCESS-KEY>;`

1. In Azure AI Search, select **Overview** from the left pane and copy the endpoint. It should be in this format: `https://demo-svc.search.windows.net`. You can then select **Settings** > **Keys** from the left pane and copy an admin key.

## Set up variables

1. Clone or download this sample repository.

1. Open `ny-philharmonic-free.rest` in Visual Studio Code.

1. Paste the variables you collected earlier:

   + Set `@baseUrl` to the search endpoint.
   + Set `@apiKey` to the admin API key of your search service.
   + Set `@storageConnectionString` to the full access connection string for your Azure Storage account.
   + Set `@blobContainer` to the name of the blob container that stores the sample data.

## Create objects and query the index

1. Send each request to create a data source, indexer, and index.

1. Send the last set of requests to query the search index.

## Next step

You can learn more about Azure AI Search on the [official documentation site](https://learn.microsoft.com/azure/search/).
