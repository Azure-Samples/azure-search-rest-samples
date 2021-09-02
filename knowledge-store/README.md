---
page_type: sample
languages:
  - rest
name: Create a Knowledge Store using REST - Postman
description: |
  A knowledge store in Azure Cognitive Search contains AI-generated content created by image and text analyses, for consumption by other processes or apps.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-knowledge-store
---

# Create a Knowledge Store in Azure Cognitive Search using REST APIs and Postman

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

This [Postman](https://www.getpostman.com/) collection uses the Azure Cognitive Search REST APIs to create the objects associated with a knowledge store: a data source, a skillset, an index, and an indexer. Requests are provided in the V2.1 collection format, which you can import and then modify for connections to your search service.

Sample data for this collection can be obtained from the [HotelReviews-Free.csv](https://knowledgestoredemo.blob.core.windows.net/hotel-reviews/HotelReviews_Free.csv?st=2019-07-29T17%3A51%3A30Z&se=2021-07-30T17%3A51%3A00Z&sp=rl&sv=2018-03-28&sr=c&sig=LnWLXqFkPNeuuMgnohiz3jfW4ijePeT5m2SiQDdwDaQ%3D) download. This file must be uploaded to Azure Blob Storage before you can send requests that create the index or knowledge store.

To use this collection in tandem with a tutorial, see [Create a knowledge store using REST](https://docs.microsoft.com/azure/search/knowledge-store-create-rest).

## Contents

| File/folder | Description |
|-------------|-------------|
| `KnowledgeStore.postman_collection.json`       | Import into Postman |
| `CONTRIBUTING.md` | Guidelines for contributing to the sample. |
| `README.md` | This README file. |
| `LICENSE.md`   | The license for the sample. |

## Prerequisites

- [Postman Desktop app](https://www.getpostman.com/)
- [Azure Cognitive Search service](https://docs.microsoft.com/azure/search/search-create-service-portal)
- [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/)

## Setup

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.

## Run the collection

This section is a high-level recap of the steps needed to send the requests and assumes familiarity with Azure Storage and Cognitive Search indexers. For a more detailed guidance, see  [Create a knowledge store using REST](https://review.docs.microsoft.com/azure/search/knowledge-store-create-rest) instead.

1. Upload [HotelReviews-Free.csv](https://knowledgestoredemo.blob.core.windows.net/hotel-reviews/HotelReviews_Free.csv) into a blob container in Azure Storage. 
1. Start Postman and import `KnowledgeStore.postman_collection.json`
1. In Postman, next to the collection name, select the ellipses menu, select **Edit**, and then select **Variables**.
1. Set `search-service-admin-key` to an `admin-key` in the search service's **Keys** page in the portal. 
1. Set `search-service-name` and `storage-account-name` to the names of your search service and storage account.
1. Set `storage-connection-string` to one of the connection strings listed in the Storage Account's **Access Keys** page in the portal.

After you complete the above steps, the requests are ready to send.

You can check the body of each request to review the object definitions. The skillset detects language, translates text (French to English, where applicable), scores sentiment, and extracts key phrases. 

Sentiment detection works best if inputs are provided in chunks or "pages". For this reason, the skillset includes a Text Split skill to parse each document into a "page" prior to enriching it.

Knowledge store specifications are found in the skillset definition. The knowledge store created by this collection consists of six tables to demonstrate various ways of capturing and projecting the original and enriched output. Projections determine which tables are created. The source can be either output from a Shaper skill, or inline shapes defined within the projection. Both approaches are demonstrated in this collection.

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

## Next steps

You can learn more about Azure Cognitive Search on the [official documentation site](https://docs.microsoft.com/azure/search).
