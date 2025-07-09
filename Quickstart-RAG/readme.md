---
page_type: sample
languages:
  - rest
name: Generative search (RAG) Quickstart
description: |
  Learn how to send search results from Azure AI Search to a chat completion model in Azure OpenAI.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-rag-quickstart
---

# Quickstart: Generative search (RAG) in Azure AI Search using REST APIs

Use this REST sample to get started with [RAG patterns](https://learn.microsoft.com/azure/search/search-agentic-retrieval-concept) in Azure AI Search. This pattern uses a chat completion model to provide a response to a query posed to your content on Azure AI Search.

This is the source code for the article: [Quickstart: Generative search (RAG) using grounding data from Azure AI Search](https://learn.microsoft.com/azure/search/search-get-started-rag?pivots=rest).

## Prerequisites

+ [Visual Studio Code](https://code.visualstudio.com/download) with a [REST client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

+ An [Azure AI Search service](https://learn.microsoft.com/azure/search/search-create-service-portal) on the Basic tier or higher with [semantic ranker enabled](https://learn.microsoft.com/azure/search/semantic-how-to-enable-disable).

+ An [Azure OpenAI resource](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource).

+ A [supported Azure OpenAI chat completion model](https://learn.microsoft.com/azure/search/search-agentic-retrieval-how-to-create#supported-models). This sample uses `gpt-4.1-mini`.

## Set up the sample

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.
1. Configure access to the Azure resources and get the endpoints. 

For connections, we recommend using Microsoft Entra ID authentication and authorization through role assignments. If you prefer, you can specify API keys on the request.

Instructions for setup are provided in the [Quickstart](https://learn.microsoft.com/azure/search/search-get-started-rag). 

## Run the code

1. Open the `rag.rest` file in Visual Studio
1. Replace the placeholder variables with valid values.
1. **Save** the file.
1. Send each request to the service.

## Next steps

You can learn more about Azure AI Search on the [official documentation site](https://learn.microsoft.com/azure/search).
