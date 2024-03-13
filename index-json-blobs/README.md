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

This sample is featured in the [Tutorial: Index JSON blobs from Azure Storage using REST](https://docs.microsoft.com/azure/search/AI-search-tutorial-blob). If you have trouble with the steps in this readme, check the tutorial for more detailed instructions.

## Prerequisites

+ [Visual Studio Code](https://code.visualstudio.com/download) with a [REST client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

+ [Azure AI Search](https://learn.microsoft.com/azure/search/). [Create](https://learn.microsoft.com//azure/search/search-create-service-portal) or [find an existing Azure AI Search resource](https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Search%2FsearchServices) under your current subscription.

+ [Azure Storage account](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal)

## Set up the data

1. Download the sample data file.

1. In Azure portal, in Azure Storage, [create a Blob container](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal) and upload the sample data files.

1. Make a note of the blob container name.

## Get connection information

Gather connection information used on the requests. You can find this information in the Azure portal. Save it in Notepad or another temporary location.

1. In Azure Storage, select **Access keys** on the left. Copy one of the connection strings. It should be in this format: `DefaultEndpointsProtocol=https;AccountName=<YOUR-STORAGE-ACCOUNT>;AccountKey=<YOUR-ACCESS-KEY>;`

1. In Azure AI Search, get the endpoint (for example, `https://demo-svc.search.windows.net`). Next, select **Keys** on the left and copy one of admin keys.

## Set up variables

1. Clone or download this sample repository.

1. Open `ny-philharmonic-free.rest` in Visual Studio Code.

1. Paste in the variables you collected earlier:

   + In `@baseUrl`, enter the search endpoint.
   + In `@apiKey`, enter the admin API key of your search service.
   + In `@storageConnectionString`, enter the full access connection string for your Azure Storage account.
   + In `@blobContainer`, enter the name of the blob container that stores the sample JSON files.

## Create objects and queryu the index

1. Send each request to create a data source, indexer, and index used in this example.

1. The last set of requests query the search index. For more information about this sample, see [Tutorial: Index JSON blobs from Azure Storage using REST](https://docs.microsoft.com/azure/search/AI-search-tutorial-blob).

## Next steps

You can learn more about Azure AI Search on the [official documentation site](https://learn.microsoft.com/azure/search/).