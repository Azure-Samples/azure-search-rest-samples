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

This is the source code for the article: [Quickstart: Semantic ranking (REST)](https://learn.microsoft.com/azure/search/search-get-started-semantic).

## Prerequisites

+ [Visual Studio Code](https://code.visualstudio.com/download) with a [REST client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

+ [Azure AI Search](https://learn.microsoft.com/azure/search/search-create-service-portal) on the Basic tier or higher with [semantic ranker enabled](https://learn.microsoft.com/azure/search/semantic-how-to-enable-disable).

## Set up the sample

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.
1. Configure access to the Azure resources and get the endpoints. 

For connections, we recommend using Microsoft Entra ID authentication and authorization through role assignments. If you prefer, you can specify API keys on the request.

Instructions for setup and finding endpoints are provided in the [Quickstart](https://learn.microsoft.com/azure/search/search-get-started-semantic). 

## Request configuration

Each request is standalone and provides the endpoints and authentication information necessary for a successful connection. The sample is set up for [Microsoft Entra ID authentication](https://learn.microsoft.com/azure/search/search-get-started-rbac), which uses your personal identity as the bearer token on the request. 

```http
@searchUrl
@personalAccessToken

### List existing indexes by name
GET  {{searchUrl}}/indexes?api-version=2024-07-01&$select=name  HTTP/1.1
Authorization: Bearer {{@personalAccessToken}}
```

Alternatively, you can run the code using an API key. If you switch to [key-based-authentication](https://learn.microsoft.com/azure/search/search-security-api-keys), be sure to change the variables and the parameters on every request.

```http
@searchUrl
@apiKey

### List existing indexes by name
GET  {{searchUrl}}/indexes?api-version=2024-07-01&$select=name  HTTP/1.1
api-key: {{apiKey}}
```

## Run the code

1. Open the `semantic-search-index-update.rest` file in Visual Studio.
1. Replace the placeholder variables with valid values.
1. **Save** the file.
1. Send each request to the service.
1. Repeat the previous steps for `semantic-search-query.rest`.

## Next steps

You can learn more about Azure AI Search on the [official documentation site](https://learn.microsoft.com/azure/search).
