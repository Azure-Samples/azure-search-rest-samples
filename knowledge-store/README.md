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

#  Creating a Knowledge Store in Azure Cognitive Search using REST APIs and Postman

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

This [Postman](https://www.getpostman.com/) collection uses the Azure Cognitive Search REST APIs to create the resources associated with a knowledge store: a data source, a skillset, an index, and an indexer. Requests are provided in the V2 collection format, which you can import and then modify for connections to your search service.

The knowledge store and index configuration are based on the source document being structured like the CSV file [HotelReviews-Free.csv](https://knowledgestoredemo.blob.core.windows.net/hotel-reviews/HotelReviews_Free.csv?st=2019-07-29T17%3A51%3A30Z&se=2021-07-30T17%3A51%3A00Z&sp=rl&sv=2018-03-28&sr=c&sig=LnWLXqFkPNeuuMgnohiz3jfW4ijePeT5m2SiQDdwDaQ%3D). This is discussed in the tutorial [Create a knowledge store using REST](https://docs.microsoft.com/azure/search/knowledge-store-create-rest).

The purpose of this sample is to demonstrate how, if you have an existing document store such as the hotel reviews CSV file, you can create a knowledge store by first creating the index, datasource, skillset, and indexer. 

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

## Setup

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.

### Running tutorial

1. Put [HotelReviews-Free.csv](https://knowledgestoredemo.blob.core.windows.net/hotel-reviews/HotelReviews_Free.csv?st=2019-07-29T17%3A51%3A30Z&se=2021-07-30T17%3A51%3A00Z&sp=rl&sv=2018-03-28&sr=c&sig=LnWLXqFkPNeuuMgnohiz3jfW4ijePeT5m2SiQDdwDaQ%3D) in Azure Blob Storage. This is discussed in the tutorial [Create a knowledge store using REST](https://review.docs.microsoft.com/azure/search/knowledge-store-create-rest).
1. Start Postman and import KnowledgeStore.postman_collection.json
1. In the collection, open the **Edit** dialog and the **Variables** tab
1. Set `admin-key`. You'll find the value for `admin-key` in the Search Service's **Keys** tab. 
1. Set `search-service-name` and `storage-account-name`. These must be set to the name of your search service and the name of the storage account at which you've stored the source document .
1. Set `storage-connection-string` to the value in the Storage Account's **Access Keys** tab. 
1. Send each request to the service.

## Next steps

You can learn more about Azure Cognitive Search on the [official documentation site](https://docs.microsoft.com/azure/search).
