---
page_type: sample
languages:
  - rest
name: Agentic Retrieval Quickstart
description: |
  Learn how to create a knowledge agent that processes conversations, retrieves information from an Azure AI Search index, and extracts answers using an Azure OpenAI model.
products:
  - azure
  - azure-cognitive-search
urlFragment: agentic-retrieval-quickstart
---

# Quickstart: Agentic retrieval in Azure AI Search using REST APIs

Use this REST sample to get started with [agentic retrieval](https://learn.microsoft.com/azure/search/search-agentic-retrieval-concept) in Azure AI Search, which integrates conversation history and Azure OpenAI models to plan, retrieve, and synthesize complex queries.

This sample is featured in the [Quickstart: Run agentic retrieval in Azure AI Search](https://learn.microsoft.com/azure/search/search-get-started-agentic-retrieval).

## Prerequisites

+ An [Azure AI Search service](https://learn.microsoft.com/azure/search/search-create-service-portal) on the Basic tier or higher with [semantic ranker enabled](https://learn.microsoft.com/azure/search/semantic-how-to-enable-disable).

+ An [Azure OpenAI resource](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource).

+ A [supported Azure OpenAI chat completion model](https://learn.microsoft.com/azure/search/search-agentic-retrieval-how-to-create#supported-models). This sample uses `gpt-4.1-mini`.

## Get connection information

This sample establishes connections to Azure AI Search and Azure OpenAI. Agentic retrieval requires these connections for document retrieval, query planning, query execution, and answer extraction.

To get connection information:

1. Sign in to the [Azure portal](https://portal.azure.com).

1. On your Azure AI Search service:

   1. From the left pane, select **Overview**.

   1. Copy the URL, which should be similar to `https://my-service.search.windows.net`.

   1. From the left pane, select **Settings** > **Keys**.

   1. Copy either API key.

1. On your Azure OpenAI resource:

   1. From the left pane, select **Resource Management** > **Keys and Endpoint**.

   1. Copy the URL, which should be similar to `https://my-resource.openai.azure.com`.

   1. Copy either API key.

## Set variables

To set connection variables:

1. Clone or download this sample repository.

1. In Visual Studio Code, open `agentic-retrieval.rest`.

1. Replace the following variables:

   + For `@baseUrl`, enter the endpoint of your Azure AI Search service.

   + For `@apiKey`, enter the API key for your Azure AI Search service.

   + For `@aoaiBaseUrl`, enter the endpoint of your Azure OpenAI resource.

   + For `@aoaiKey`, enter the API key for your Azure OpenAI resource.

## Run the code

For each request in this sample, select **Send request**. The requests create a search index, load documents into the index, create a knowledge agent, and run the retrieval pipeline.
