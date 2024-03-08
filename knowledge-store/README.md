---
page_type: sample
languages:
  - rest
name: Create a Knowledge Store using REST
description: |
  A knowledge store in Azure AI Search contains AI-generated content created by image and text analyses, for consumption by other processes or apps.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-knowledge-store
---

# Create a knowledge store in Azure AI Search using REST APIs

This sample applies to [knowledge stores](https://learn.microsoft.com/azure/search/knowledge-store-concept-intro) in Azure AI Search. It uses the Azure AI Search REST APIs to create an indexer, data source, index, and skillset that applies AI processing. It uses Azure Storage for durable storage of a knowledge store.

This example is featured in the [Create a knowledge store using REST](hhttps://learn.microsoft.com/azure/search/knowledge-store-create-rest).
 
## Prerequisites

+ [Visual Studio Code](https://code.visualstudio.com/download) with a [REST client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

+ [Azure AI Search](https://learn.microsoft.com/azure/search/). [Create](https://learn.microsoft.com//azure/search/search-create-service-portal) or [find an existing Azure AI Search resource](https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Search%2FsearchServices) under your current subscription.

+ [Azure Storage account](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal)

+ [HotelReviews-Free.csv](https://github.com/Azure-Samples/azure-search-sample-data/tree/main/hotelreviews) 

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

1. Open `knowledge-store.rest` in Visual Studio Code.

1. Paste in the variables you collected earlier:

   + In `@baseUrl`, enter the search endpoint.
   + In `@apiKey`, enter the admin API key of your search service.
   + In `@storageConnectionString`, enter the full access connection string for your Azure Storage account.
   + In `@blobContainer`, enter the name of the blob container that stores the clinical trials documents.

## Run the code

Send each request to create a data source, indexer, skillset, and index used in this example.

Sentiment detection works best if inputs are provided in chunks or "pages". For this reason, the skillset includes a Text Split skill to parse each document into a "page" prior to enriching it.

Knowledge store specifications are found in the skillset definition. The knowledge store consists of six tables to demonstrate various ways of capturing and projecting the original and enriched output. Projections determine which tables are created. The source can be either output from a Shaper skill, or inline shapes defined within the projection. Both approaches are demonstrated in this example.

## Check results

After you send each request, the search service should respond with a 201 success message. If you get errors, re-check your variables and make sure that the search service has room for the new index, indexer, data source, and skillset (the free tier is limited to three of each).

For verification, use Search explorer to query the index and Storage Explorer to view the tables in Azure Storage. You should see the following 6 tables:

- hotelReviews1Document (contains fields from the CSV, such as reviews_date and reviews_text)
- hotelReviews2Pages (contains enriched fields, such as sentiment score and key phrases)
- hotelReviews3KeyPhrases (contains just the key phrases)
- hotelReviews4InlineProjectionDocument (alternative to the first table, using inline projections instead of Shaper)
- hotelReviews5InlineProjectionPages (alternative to the second table, using inline projections instead of Shaper)
- hotelreviews6InlineProjectionKeyPhrases (alternative to the third table, using inline projections instead of Shaper)

Each table is generated with the IDs necessary for cross-linking the tables in queries, for table  projections that are in the same projection group.
