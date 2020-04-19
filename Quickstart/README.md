---
page_type: sample
languages:
  - rest
name: "Quickstart in REST - Postman"
description: |
  Learn how to create, load, and query an Azure Cognitive Search index using Postman and the latest-version REST APIs.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-quickstart
---

# Quickstart sample for Azure Cognitive Search using REST APIs and Postman

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

Demonstrates using Postman and the Azure Cognitive Search REST APIs to send requests: create an index, load it with documents, and execute a few queries. Requests are provided in the V2 collection format, which you can import and then modify for connections to your search service.

This collection is featured in the [Quickstart: Create a search index in Postman using REST APIs](https://docs.microsoft.com/azure/search/search-get-started-postman). When you import the collection, modify the headers and URL to use your service name and API key. The index is modeled on a subset of the Hotels dataset, reduced for readability and comprehension. Index definition and documents are included in the code.

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
- [Azure Cognitive Search service](https://docs.microsoft.com/azure/search/search-create-service-portal)

## Setup

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.

### Running quickstart
1. Start Postman and import AzureSearchQuickstart.postman_collection.json
1. For each request, update the Header to use the admin api-key of your service, which you can obtain from the portal.
1. Next, update the URL of each request to use the name of your search service.
1. Send each request to the service.

## Next steps

You can learn more about Azure Cognitive Search on the [official documentation site](https://docs.microsoft.com/azure/search).
