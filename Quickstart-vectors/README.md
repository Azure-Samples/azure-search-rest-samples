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

Demonstrates the Azure AI Search REST APIs to send requests: create an index, load it with vector, and execute a few vectorqueries. Requests are provided in an `az-search-vector-quickstart.rest` file, which you can open and then modify for connections to your search service.

This is the source code for the article: [Quickstart: Vector search with REST](https://learn.microsoft.com/azure/search/search-get-started-vector). 

## Prerequisites

+ [Visual Studio Code](https://code.visualstudio.com/download) with a [REST client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

+ [Azure AI Search](https://learn.microsoft.com/azure/search/search-create-service-portal), any tier.

+ (Optional) [Semantic ranking](https://learn.microsoft.com/azure/search/semantic-how-to-enable-disable) enabled on Azure AI Search if you want to run the hybrid query that invokes semantic ranking.

+ (Optional) [Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource) with a deployment of **text-embedding-3-small** if you want to generate your own embeddings. Otherwise, use the embedded vectors provided in the sample.

## Set up the sample

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.
1. Configure access to the Azure resources and get the endpoints. 

For connections, we recommend using Microsoft Entra ID authentication and authorization through role assignments. If you prefer, you can specify API keys on the request.

Instructions for setup are provided in the [Quickstart](https://learn.microsoft.com/azure/search/search-get-started-vector). 

## Run the code

1. Open the `az-search-quickstart-vectors.rest` file in Visual Studio
1. Replace the placeholder variables with valid values.
1. **Save** the file.
1. Send each request to the service.

## Next steps

You can learn more about Azure AI Search on the [official documentation site](https://learn.microsoft.com/azure/search).
