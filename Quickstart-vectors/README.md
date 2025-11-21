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

# Quickstart: Vectors in Azure AI Search using REST APIs

This sample demonstrates how to use the Azure AI Search REST APIs to create an index, load it with vectors, and execute vector queries. Requests are provided in an `az-search-vector-quickstart.rest` file, which you can open and modify to connect to your search service.

This sample is the source code for [Quickstart: Vector search using REST](https://learn.microsoft.com/azure/search/search-get-started-vector?tabs=keyless&pivots=rest).

## Prerequisites

+ An [Azure AI Search service](https://learn.microsoft.com/azure/search/search-create-service-portal) on any pricing tier.

+ (Optional) [Semantic ranking](https://learn.microsoft.com/azure/search/semantic-how-to-enable-disable) enabled on Azure AI Search if you want to run the hybrid query that invokes semantic ranking.

+ (Optional) [Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource) with a `text-embedding-3-small` deployment if you want to generate your own embeddings. Otherwise, use the embedded vectors provided in the sample.

+ [Visual Studio Code](https://code.visualstudio.com/download) with the [REST Client extension](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

## Set up the sample

1. Clone or download this sample repository.

1. If the download is a ZIP file, extract its contents. Make sure the files are read-write.

1. Configure access to the Azure resources and get their connection information.

For connections, we recommend Microsoft Entra ID for authentication and role assignments for authorization. Alternatively, you can specify [API keys](https://learn.microsoft.com/azure/search/search-security-api-keys) in your requests. [Quickstart: Vector search using REST](https://learn.microsoft.com/azure/search/search-get-started-vector?tabs=keyless&pivots=rest) provides the full setup instructions.

## Run the code

1. Open the `az-search-quickstart-vectors.rest` file in Visual Studio Code.

1. Replace the placeholder variables with valid values.

1. Save the file.

1. Send each request to your Azure AI Search service.

## Next step

You can learn more about Azure AI Search on the [official documentation site](https://learn.microsoft.com/azure/search).
