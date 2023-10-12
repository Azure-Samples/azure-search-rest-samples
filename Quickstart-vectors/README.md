---
page_type: sample
languages:
  - rest
name: "Vector quickstart in REST - Postman"
description: |
  Learn how to create, load, and query vectors in Azure Cognitive Search using Postman and REST APIs.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-vector-quickstart
---

# Quickstart for vectors in Azure Cognitive Search using REST APIs and Postman

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

Demonstrates using Postman and the Azure Cognitive Search REST APIs to send vector requests: create an index with vector fields, load it with documents that contain embeddings, and execute a few vector queries. Requests are provided in the V2 collection format, which you can import and then modify for connections to your search service.

This collection is featured in the [Quickstart: Vector search indexing and queries](https://docs.microsoft.com/azure/search/search-get-started-vectors). When you import the collection, modify the headers and URL to use your Azure resources. The index is modeled on a subset of the Hotels dataset, reduced for readability and comprehension. Index definition and documents are included in the code.

## Prerequisites

- [Postman Desktop app](https://www.getpostman.com/)
- [Azure Cognitive Search service](https://docs.microsoft.com/azure/search/search-create-service-portal)
- (optional) [Semantic ranking](https://learn.microsoft.com/azure/search/semantic-how-to-enable-disable) if you want to run the hybrid query that invokes semantic ranking
- (optional) [Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource) with a deployment of **text-embedding-ada-002** if you want to generate embeddings (the sample comes with vectors, so prerequisite is only needed if you want different vectors.)

## Setup

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.

### Running quickstart

1. Start Postman and import `AzureSearchQuickstartVectors 2023-10-01-Preview.postman_collection.json`
1. Select the collection, open the actions menu, select **Edit**.
1. Enter the name of your search service and an admin API key, which you can [obtain from the Azure portal](https://learn.microsoft.com/azure/search/search-get-started-vectors#copy-a-key-and-url).
1. Select **Save**.
1. Send each request to the service.

## Next steps

You can learn more about Azure Cognitive Search on the [official documentation site](https://docs.microsoft.com/azure/search).
