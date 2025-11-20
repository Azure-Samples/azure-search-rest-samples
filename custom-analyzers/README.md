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

This sample creates a search index and builds a custom analyzer designed to handle phone numbers. Phone numbers are ideal candidates for custom analyzers because of the variety of formats and special characters associated with them. The HTTP requests demonstrate the process of testing sample searches and lexical analysis and building an analyzer for intuitively searching phone numbers.

This sample is featured in [Tutorial: Create a custom analyzer using REST APIs](https://learn.microsoft.com/azure/search/tutorial-create-custom-analyzer).

## Prerequisites

+ An [Azure AI Search service](https://learn.microsoft.com/azure/search/search-create-service-portal) on any pricing tier.

+ [Visual Studio Code](https://code.visualstudio.com/download) with the [REST Client extension](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

## Get connection information

Gather connection information used on the requests. You can find this information in the Azure portal. Save it in Notepad or another temporary location.

1. In the Azure portal, select **Overview** from the left pane and copy the endpoint. It should be in this format: `https://demo-svc.search.windows.net`.

1. Select **Settings** > **Keys** from the left pane and copy an admin key.

## Set up variables

1. Clone or download this sample repository.

1. Open `custom-analyzers.rest` in Visual Studio Code. For help with setting up Visual Studio Code, see [Quickstart: Full-text search using REST](https://learn.microsoft.com/azure/search/search-get-started-text?tabs=keyless%2Cwindows&pivots=rest).

1. Paste the variables you collected earlier:

   + In `@baseUrl`, enter the search endpoint.
   + In `@apiKey`, enter the admin API key of your search service.

## Run the code

For each request, select **Send Request**.

## Next step

You can learn more about Azure AI Search on the [official documentation site](https://learn.microsoft.com/azure/search/).
