---
page_type: sample
languages:
  - rest
name: Agentic Retrieval Quickstart
description: |
  Learn how to create a knowledge base that retrieves content from an Azure AI Search index and uses an LLM from Azure OpenAI in Foundry Models to generate answers.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-agentic-retrieval-quickstart
---

# Quickstart: Agentic retrieval in Azure AI Search using REST APIs

Use this REST sample to get started with [agentic retrieval](https://learn.microsoft.com/azure/search/search-agentic-retrieval-concept) in Azure AI Search, which integrates an LLM from Azure OpenAI in Foundry Models to process queries, retrieve relevant content from indexed documents, and synthesize answers in natural language.

This sample is the source code for the REST portion of [Quickstart: Use agentic retrieval in Azure AI Search](https://learn.microsoft.com/azure/search/search-get-started-agentic-retrieval).

## Prerequisites

+ An [Azure AI Search service](https://learn.microsoft.com/azure/search/search-create-service-portal) on the Basic tier or higher with [semantic ranker enabled](https://learn.microsoft.com/azure/search/semantic-how-to-enable-disable).

+ An [Azure AI Foundry project](https://learn.microsoft.com/azure/ai-foundry/how-to/create-projects) and Azure AI Foundry resource. When you create a project, the resource is automatically created.

+ A [supported LLM](https://learn.microsoft.com/azure/search/search-agentic-retrieval-how-to-create#supported-models). This sample uses `gpt-5-mini`.

+ A text embedding model. This sample uses `text-embedding-3-large`.

+ [Visual Studio Code](https://code.visualstudio.com/download) with the [REST Client extension](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

## Set up the sample

1. Clone or download this sample repository.
1. If the download is a ZIP file, extract its contents. Make sure the files are read-write.
1. Configure access to the Azure resources and get their endpoints.

For connections, we recommend Microsoft Entra ID for authentication and role assignments for authorization. Alternatively, you can specify [API keys](https://learn.microsoft.com/azure/search/search-security-api-keys) in your requests.

[Quickstart: Use agentic retrieval in Azure AI Search](https://learn.microsoft.com/azure/search/search-get-started-agentic-retrieval) provides the full setup instructions.

## Run the code

1. In Visual Studio Code, open the `agentic-retrieval.rest` file.
1. Replace the placeholder variables with valid values.
1. Save the file.
1. Send each request to your Azure AI Search service.

## Next step

Learn more about Azure AI Search on the [official documentation site](https://learn.microsoft.com/azure/search).
