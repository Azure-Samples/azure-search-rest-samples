---
page_type: sample
languages:
  - rest
name: Semantic ranker Quickstart
description: |
  Learn how to add a semantic configuration to an Azure AI Search index, and add semantic parameters that invoke semantic ranking on queries.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-semantic-search-quickstart
---

# Quickstart: Semantic ranking in Azure AI Search using REST APIs

Azure AI Search supports secondary L2 ranking that rescores initial results using machine reading comprehension models. The L2 ranker promotes more semantically relevant matches to the top.

This sample is the source code for [Quickstart: Semantic ranking using REST](https://learn.microsoft.com/azure/search/search-get-started-semantic?pivots=rest).

## Prerequisites

+ An [Azure AI Search](https://learn.microsoft.com/azure/search/search-create-service-portal) service with [semantic ranker enabled](https://learn.microsoft.com/azure/search/semantic-how-to-enable-disable).

+ [Visual Studio Code](https://code.visualstudio.com/download) with the [REST Client extension](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

## Set up the sample

1. Clone or download this sample repository.

1. If the download is a ZIP file, extract its contents. Make sure the files are read-write.

1. Configure access to the Azure resources and get their connection information.

For connections, we recommend Microsoft Entra ID for authentication and role assignments for authorization. Alternatively, you can specify [API keys](https://learn.microsoft.com/azure/search/search-security-api-keys) in your requests. [Quickstart: Semantic ranking using REST](https://learn.microsoft.com/azure/search/search-get-started-semantic?pivots=rest) provides the full setup instructions.

## Run the code

1. Open the `semantic-search-index-update.rest` file in Visual Studio Code.

1. Replace the placeholder variables with valid values.

1. Save the file.

1. Send each request to your Azure AI Search service.

1. Repeat the previous steps for the `semantic-search-query.rest` file.

## Next step

You can learn more about Azure AI Search on the [official documentation site](https://learn.microsoft.com/azure/search).
