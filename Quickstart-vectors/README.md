---
page_type: sample
languages:
  - rest
name: "Vector quickstart in REST"
description: |
  Learn how to create, load, and query vectors in Azure AI Search using REST APIs.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-vector-quickstart
---

# Quickstart for vectors in Azure AI Search using REST

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

Demonstrates the Azure AI Search REST APIs to send requests: create an index, load it with vector, and execute a few vectorqueries. Requests are provided in an `az-search-vector-quickstart.rest` file, which you can open and then modify for connections to your search service.

These requests are explained in the [Quickstart: Vector search with REST](https://learn.microsoft.com/azure/search/search-get-started-vector) article. 

## Prerequisites

+ [Visual Studio Code](https://code.visualstudio.com/download) with a [REST client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

+ [Azure AI Search](search-what-is-azure-search.md). [Create](search-create-service-portal.md) or [find an existing Azure AI Search resource](https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Search%2FsearchServices) under your current subscription. You can use a free service for this quickstart. 

+ (Optional) [Semantic ranking](https://learn.microsoft.com/azure/search/semantic-how-to-enable-disable) enabled on Azure AI Search if you want to run the hybrid query that invokes semantic ranking.

+ (Optional) [Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource) with a deployment of **text-embedding-3-small** if you want to generate your own embeddings. Otherwise, use the embedded vectors provided in the sample.

## Set up the sample

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.

We recommend using Microsoft Entra ID authentication and authorization through role assignments. If you prefer, you can specify API keys on the request. Instructions are provided in the [Quickstart](https://learn.microsoft.com/azure/search/search-get-started-vectors). 

## Run the code

1. Start Visual Studio Code and open the `az-search-quickstart.rest` file.
1. Provide a valid search service name and API key or Authorization bearer token in the variables.
1. **Save** the file.
1. Send each request to the service.

## Next steps

You can learn more about Azure AI Search on the [official documentation site](https://docs.microsoft.com/azure/search).
