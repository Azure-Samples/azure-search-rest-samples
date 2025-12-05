---
page_type: sample
languages:
  - rest
name: Debug skillsets in Azure AI Search
description: |
  Learn how the Debug Sessions visual editor can help you fix enrichment pipeline issues in Azure AI Search. This collection creates a skillset with invalid fields and missing data, easily fixed in a debug session.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-debug-sessions
---

# Fix skillset issues using Debug Sessions in Azure AI Search

This sample uses the Azure AI Search REST APIs to create a "buggy" enrichment pipeline. You can use the Debug Sessions visual editor in the Azure portal to fix the warnings.

## Prerequisites

+ An [Azure AI Search service](https://learn.microsoft.com/azure/search/search-create-service-portal) on any pricing tier.

+ An [Azure Storage account](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal).

+ [Visual Studio Code](https://code.visualstudio.com/download) with the [REST Client extension](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

## Set up the data

1. [Download the sample data files](https://github.com/Azure-Samples/azure-search-sample-data/tree/main/_ARCHIVE/clinical-trials/clinical-trials-pdf-19). Sample data consists of 19 clinical trial PDFs.

1. In the Azure portal, [create a blob container](https://learn.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal) and upload the 19 documents.

1. Make a note of the blob container name.

## Get connection information

Gather connection information used in the requests. You can find this information in the Azure portal. Save it in a temporary location, such as Notepad.

1. In Azure Storage, select **Security + networking** > **Access keys** from the left pane and copy a connection string. It should be in this format: `DefaultEndpointsProtocol=https;AccountName=<YOUR-STORAGE-ACCOUNT>;AccountKey=<YOUR-ACCESS-KEY>;`

1. In Azure AI Search, select **Overview** from the left pane and copy the endpoint. It should be in this format: `https://my-service.search.windows.net`. You should then select **Settings** > **Keys** from the left pane and copy an admin key.

## Set up variables

1. Clone or download this sample repository.

1. Open `debug-sessions.rest` in Visual Studio Code. For help with setting up Visual Studio Code, see [Quickstart: Full-text search using REST](https://learn.microsoft.com/azure/search/search-get-started-text?tabs=keyless%2Cwindows&pivots=rest).

1. Paste the variables you collected earlier:

   + Set `@baseUrl` to the endpoint of your search service.
   + Set `@apiKey` to the admin API key of your search service.
   + Set `@storageConnectionString` to the full-access connection string for your Azure Storage account.
   + Set `@blobContainer` to the name of the blob container that stores the sample data.

## Create objects and debug the skillset

1. Send each request to create a data source, indexer, skillset, and index.

1. In the Azure portal, find your search service, select the skillset, and start a debug session.

1. For the remaining steps, continue with [Tutorial: Debug a skillset using Debug Sessions](https://learn.microsoft.com/azure/search/cognitive-search-tutorial-debug-sessions).

## Next step

You can learn more about Azure AI Search on the [official documentation site](https://learn.microsoft.com/azure/search/).