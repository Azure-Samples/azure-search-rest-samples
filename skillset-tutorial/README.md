---
page_type: sample
languages:
  - rest
name: Skillset Tutorial in REST
description: |
  Create a skillset in Azure AI Search to extract searchable information and structure from Azure blobs.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-tutorial
---

# Create a skillset in Azure AI Search using REST APIs

This sample uses the Azure AI Search REST APIs to create an indexer, data source, index, and skillset that applies AI processing to Azure blobs during indexing.

Skillset steps include optical character recognition (OCR), language detection, entity recognition, and key phrase extraction. The sample demo files consist of multiple content types ranging from image-only, text-only, and rich application files with embedded images and text. The end result is a searchable index that you can query for new and enriched content.

This sample is featured in [Tutorial: Skillsets in Azure AI Search](https://learn.microsoft.com/azure/search/tutorial-skillset?pivots=rest).

## Prerequisites

+ An [Azure AI Search service](https://learn.microsoft.com/azure/search/search-create-service-portal) on any pricing tier.

+ An [Azure Storage account](https://learn.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal).

+ [Visual Studio Code](https://code.visualstudio.com/download) with the [REST Client extension](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

## Set up the data

1. Download the [sample data](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/ai-enrichment-mixed-media).

1. In the Azure portal, [create a blob container](https://learn.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal) and upload the sample data files.

1. Make a note of the blob container name.

## Get connection information

Gather connection information used in the requests. You can find this information in the Azure portal. Save it in a temporary location, such as Notepad.

1. In Azure Storage, select **Security + networking** > **Access keys** from the left pane and copy a connection string. It should be in this format: `DefaultEndpointsProtocol=https;AccountName=<YOUR-STORAGE-ACCOUNT>;AccountKey=<YOUR-ACCESS-KEY>;`

1. In Azure AI Search, select **Overview** from the left pane and copy the endpoint. It should be in this format: `https://my-service.search.windows.net`. You should then select **Settings** > **Keys** from the left pane and copy an admin key.

## Set up variables

1. Clone or download this sample repository.

1. Open `skillset-tutorial.rest` in Visual Studio Code.

1. Paste the variables you collected earlier:

   + Set `@baseUrl` to the endpoint of your search service.
   + Set `@apiKey` to the admin API key of your search service.
   + Set `@storageConnectionString` to the full-access connection string for your Azure Storage account.
   + Set `@blobContainer` to the name of the blob container that stores the sample data.

## Create objects and query the index

1. Send each request to create a data source, indexer, skillset, and index.

1. Send the last set of requests to query the search index.

## Next step

You can learn more about Azure AI Search on the [official documentation site](https://learn.microsoft.com/azure/search/).
