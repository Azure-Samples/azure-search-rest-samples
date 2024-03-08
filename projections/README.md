
# Readme for projection examples for Azure AI Search skillsets

This sample applies to [knowledge stores](https://learn.microsoft.com/azure/search/knowledge-store-concept-intro) in Azure AI Search. It uses the Azure AI Search REST APIs to create an indexer, data source, index, and skillset that applies AI processing. It includes an initial skillset, plus four additional skillsets that focus on projection definitions variants.

This example is featured in the [Detailed example of shapes and projections in a knowledge store](https://learn.microsoft.com/en-us/azure/search/knowledge-store-projection-example-long).
 
## Prerequisites

+ [Visual Studio Code](https://code.visualstudio.com/download) with a [REST client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

+ [Azure AI Search](https://learn.microsoft.com/azure/search/). [Create](https://learn.microsoft.com//azure/search/search-create-service-portal) or [find an existing Azure AI Search resource](https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Search%2FsearchServices) under your current subscription.

+ [Azure Storage account](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal)

+ [Sample data files (mixed media)](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/ai-enrichment-mixed-media)

## Set up the data

1. Download the sample data files.

1. In Azure portal, in Azure Storage, [create a Blob container](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal) and upload the sample data files.

1. Make a note of the blob container name.

## Get connection information

Gather connection information used on the requests. You can find this information in the Azure portal. Save it in Notepad or another temporary location.

1. In Azure Storage, select **Access keys** on the left. Copy one of the connection strings. It should be in this format: `DefaultEndpointsProtocol=https;AccountName=<YOUR-STORAGE-ACCOUNT>;AccountKey=<YOUR-ACCESS-KEY>;`

1. In Azure AI Search, get the endpoint (for example, `https://demo-svc.search.windows.net`). Next, select **Keys** on the left and copy one of admin keys.

## Set up variables

1. Clone or download this sample repository.

1. Open `projections.rest` in Visual Studio Code.

1. Paste in the variables you collected earlier:

   + In `@baseUrl`, enter the search endpoint.
   + In `@apiKey`, enter the admin API key of your search service.
   + In `@storageConnectionString`, enter the full access connection string for your Azure Storage account.
   + In `@blobContainer`, enter the name of the blob container that stores the clinical trials documents.

## Run the code

1. Send each request to create a data source, indexer, skillset, and index used in this example.

1. The last set of requests query the search index. For more information about this sample, see [Detailed example of shapes and projections in a knowledge store](https://learn.microsoft.com/en-us/azure/search/knowledge-store-projection-example-long).
