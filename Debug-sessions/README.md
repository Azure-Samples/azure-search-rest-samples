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

This sample uses the Azure AI Search REST APIs to create a "buggy" enrichment pipeline with warnings you can fix in the Debug Sessions visual editor in the Azure portal.

## Prerequisites

+ [Visual Studio Code](https://code.visualstudio.com/download) with a [REST client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

+ [Azure AI Search](https://learn.microsoft.com/azure/search/). [Create](https://learn.microsoft.com//azure/search/search-create-service-portal) or [find an existing Azure AI Search resource](https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Search%2FsearchServices) under your current subscription.

+ [Azure Storage account](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal)

+ [Clinical Trials Data (19 documents)](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/clinical-trials-pdf-19)

## Set up the data

1. Download the clinical trials data set.

1. In Azure portal, in Azure Storage, [create a Blob container](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal) and upload the 19 documents.

1. Make a note of the blob container name.

## Get connection information

Gather connection information used on the requests. You can find this information in the Azure portal. Save it in Notepad or another temporary location.

1. In Azure Storage, select **Access keys** on the left. Copy one of the connection strings. It should be in this format: `DefaultEndpointsProtocol=https;AccountName=<YOUR-STORAGE-ACCOUNT>;AccountKey=<YOUR-ACCESS-KEY>;`

1. In Azure AI Search, get the endpoint (for example, `https://demo-svc.search.windows.net`). Next, select **Keys** on the left and copy one of admin keys.

## Set up variables

1. Clone or download this sample repository.

1. Open `debug-sessions-tutorial.rest` in Visual Studio Code. If you need help with Visual Studio Code setup, see [Quickstart: Text search using REST](https://learn.microsoft.com/azure/search/search-get-started-rest).

1. Paste in the variables you collected earlier:

   + In `@baseUrl`, enter the search endpoint.
   + In `@apiKey`, enter the admin API key of your search service.
   + In `@storageConnectionString`, enter the connection string for your Azure Storage account.
   + In `@blobContainer`, enter the name of the blob container that stores the clinical trials documents.

## Create objects and debug the skillset

1. Send each request to create a data source, indexer, skillset, and index used in this example.

1. Open Azure portal, find your search service, select the skillset, and start a debug session. 

1. For the remaining steps, continue with [Tutorial: Debug a skillset using Debug Sessions](https://learn.microsoft.com/azure/search/cognitive-search-tutorial-debug-sessions).
