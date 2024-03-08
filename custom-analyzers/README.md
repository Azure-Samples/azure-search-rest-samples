---
page_type: sample
languages:
  - rest
name: Custom Analyzer Tutorial
description: |
  Learn how to create a custom analyzer in Azure AI Search to intuitively search across phone numbers or other content.
products:
  - azure
  - azure-cognitive-search
urlFragment: custom-analyzer-tutorial
---

# Create a custom analyzer in Azure AI Search using REST APIs

This sample creates a search index and builds a custom analyzer designed for handling phone numbers. Phone numbers are a good candidate for custom analyzers due to the multiple formats and special characters that exist for this type of content. The HTTP requests step through the process of testing sample searches, testing lexical analysis, and building an analyzer to intuitively search phone numbers.

This sample is featured in the [Tutorial: Create a custom analyzer using REST APIs](https://learn.microsoft.com/azure/search/tutorial-create-custom-analyzer).

## Prerequisites

+ [Visual Studio Code](https://code.visualstudio.com/download) with a [REST client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

+ [Azure AI Search](https://learn.microsoft.com/azure/search/). [Create](https://learn.microsoft.com//azure/search/search-create-service-portal) or [find an existing Azure AI Search resource](https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Search%2FsearchServices) under your current subscription.

## Get connection information

Gather connection information used on the requests. You can find this information in the Azure portal. Save it in Notepad or another temporary location.

1. In Azure portal, get the search service endpoint (for example, `https://demo-svc.search.windows.net`). 

1. Next, select **Keys** on the left and copy one of admin keys.

## Set up variables

1. Clone or download this sample repository.

1. Open `custom-analyzers.rest` in Visual Studio Code. If you need help with Visual Studio Code setup, see [Quickstart: Text search using REST](https://learn.microsoft.com/azure/search/search-get-started-rest).

1. Paste in the variables you collected earlier:

   + In `@baseUrl`, enter the search endpoint.
   + In `@apiKey`, enter the admin API key of your search service.

## Run the code

1. For each request, select **Send request**. 

1. For an explanation of the code, see [Tutorial: Create a custom analyzer using REST APIs](https://learn.microsoft.com/azure/search/tutorial-create-custom-analyzer).
