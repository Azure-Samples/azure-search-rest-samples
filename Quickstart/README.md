---
page_type: sample
languages:
  - rest
name: "Quickstart in REST"
description: |
  Learn how to create, load, and query an Azure AI Search index using the REST APIs.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-quickstart
---

# Quickstart for Azure AI Search using REST APIs

Demonstrates the Azure AI Search REST APIs to send requests: create an index, load it with documents, and execute a few queries. Requests are provided in an `az-search-quickstart.rest` file, which you can open and then modify for connections to your search service.

This is the source code for the article: [Quickstart: Text search with REST](https://learn.microsoft.com/azure/search/search-get-started-rest). 

## Prerequisites

+ [Visual Studio Code](https://code.visualstudio.com/download) with a [REST client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

+ [Azure AI Search](https://learn.microsoft.com/azure/search/search-create-service-portal), any tier.

## Set up the sample

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.

We recommend using Microsoft Entra ID authentication and authorization through role assignments. If you prefer, you can specify API keys on the request. Instructions are provided in the [Quickstart](https://learn.microsoft.com/azure/search/search-get-started-rest). 

## Run the code

1. Open the `az-search-quickstart.rest` file in Visual Studio
1. Replace the placeholder variables with valid values.
1. **Save** the file.
1. Send each request to the service.

## Next steps

You can learn more about Azure AI Search on the [official documentation site](https://learn.microsoft.com/azure/search).
