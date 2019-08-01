---
page_type: sample
languages:
  - rest
name: Quickstart in REST - Postman
description: |
  Postman V2 collection containing REST API calls to Azure Search, demonstrating index definition, data ingestion, and query execution.
products:
  - azure
  - azure-search
urlFragment: rest-api-quickstart
---

# Quickstart for Azure Search using REST APIs and Postman

Demonstrates using Postman and the Azure Search REST APIs to send requests to Azure Search: create an index, load it with documents, and execute a few queries. Requests are provided in the V2 collection format, which you can import and then modify for connections to your Azure Search service.

This collection is featured in the [Quickstart: Create an Azure Search index in Postman using REST APIs](https://docs.microsoft.com/azure/search/search-get-started-postman). When you import the collection, modify the headers and URL to use your service name and API key. The index is modeled on a subset of the Hotels dataset, reduced for readability and comprehension. Index definition and documents are included in the code.

## Contents

| File/folder | Description |
|-------------|-------------|
| `Quickstart`       | Contains AzureSearchQuickstart.postman_collection.json, which you can import into Postman |
| `.gitignore` | Define what to ignore at commit time. |
| `CONTRIBUTING.md` | Guidelines for contributing to the sample. |
| `README.md` | This README file. |
| `LICENSE`   | The license for the sample. |

## Prerequisites

- [Postman Desktop app](https://www.getpostman.com/)
- [Azure Search service](https://docs.microsoft.com/azure/search/search-create-service-portal)

## Setup

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.

### Running quickstart
1. Start Postman and import AzureSearchQuickstart.postman_collection.json
1. For each request, update the Header to use the admin api-key of your service, which you can obtain from the portal.
1. Next, update the URL of each request to use the name of your search service.
1. Send each request to the service.