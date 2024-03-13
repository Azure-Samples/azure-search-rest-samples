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

These requests are explained in the [Quickstart: Text search with REST](https://learn.microsoft.com/azure/search/search-get-started-rest) article. 

## Prerequisites

+ [Visual Studio Code](https://code.visualstudio.com/download) with a [REST client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

+ [Azure AI Search](search-what-is-azure-search.md). [Create](search-create-service-portal.md) or [find an existing Azure AI Search resource](https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Search%2FsearchServices) under your current subscription. You can use a free service for this quickstart. 

## Set up the sample

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.

## Run the code

1. Start Visual Studio Code and open the `az-search-quickstart.rest` file.
1. Provide a valid search service name and API key in the variables.
1. **Save** the file.
1. Send each request to the service.

## Next steps

You can learn more about Azure AI Search on the [official documentation site](https://docs.microsoft.com/azure/search).
