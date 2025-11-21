---
page_type: sample
languages:
  - rest
name: Projection examples for Azure AI Search skillsets
description: |
  Learn how to use projections in Azure AI Search skillsets to shape and transform your data.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-projection-examples
---

# Projection examples for Azure AI Search skillsets

This sample applies to [knowledge stores](https://learn.microsoft.com/azure/search/knowledge-store-concept-intro) in Azure AI Search. It uses the Azure AI Search REST APIs to create an indexer, data source, index, and skillset that applies AI processing. It includes an initial skillset, plus four additional skillsets that focus on projection definitions variants.

This example is featured in the [Example of shapes and projections in a knowledge store](https://learn.microsoft.com/azure/search/knowledge-store-projection-example-long).

## Prerequisites

+ An [Azure AI Search service](https://learn.microsoft.com/azure/search/search-create-service-portal) on any pricing tier.

+ A [Microsoft Foundry resource](https://learn.microsoft.com/azure/ai-services/multi-service-resource) in the same region as Azure AI Search. This is important for getting the free transactions for AI enrichment.

+ An [Azure Storage account](https://learn.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal).

+ [Visual Studio Code](https://code.visualstudio.com/download) with the [REST Client extension](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

## Set up the data

1. [Download the sample data files](https://github.com/Azure-Samples/azure-search-sample-data/tree/main/ai-enrichment-mixed-media). Sample data consists of 14 files of mixed content types.

1. In the Azure portal, [create a blob container](https://learn.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal) and upload the sample data files.

1. Make a note of the blob container name.

## Get Azure Storage connection information

Gather connection information used in the requests. You can find this information in the Azure portal. Save it in a temporary location, such as Notepad.

1. In Azure Storage, select **Security + networking** > **Access keys** from the left pane and copy a connection string. It should be in this format: `DefaultEndpointsProtocol=https;AccountName=<YOUR-STORAGE-ACCOUNT>;AccountKey=<YOUR-ACCESS-KEY>;`

1. In Azure AI Search, select **Overview** from the left pane and copy the endpoint. It should be in this format: `https://demo-svc.search.windows.net`. You can then select **Settings** > **Keys** from the left pane and copy an admin key.

## Set up variables

1. Clone or download this sample repository.

1. Open `projections.rest` in Visual Studio Code.

1. Paste the variables you collected earlier:

   + Set `@baseUrl` to the endpoint of your search service.
   + Set `@apiKey` to the admin API key of your search service.
   + Set `@storageConnectionString` to the full-access connection string for your Azure Storage account.
   + Set `@blobContainer` to the name of the blob container that stores the sample data.

## Run the code

1. Send each request to create a data source, indexer, skillset, and index.

1. Send the last set of requests to query the search index.

## Next step

You can learn more about Azure AI Search on the [official documentation site](https://learn.microsoft.com/azure/search/).
