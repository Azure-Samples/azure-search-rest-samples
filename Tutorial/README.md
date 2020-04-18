---
page_type: sample
languages:
  - rest
name: Skillset Tutorial in REST - Postman
description: |
  Learn how to create an enrichment pipeline in Azure Cognitive Search to extract information and structure from unstructured blobs.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-tutorial
---

#  Create a cognitive skillset in Azure Cognitive Search using REST APIs and Postman

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

Demonstrates using Postman and the Azure Cognitive Search REST APIs to send requests: create a data source, a skillset, index, and indexer. Requests are provided in the V2 collection format, which you can import and then modify for connections to your search service.

This collection is featured in the [Tutorial: Add structure to "unstructured content" using REST APIs](https://docs.microsoft.com/azure/search/cognitive-search-tutorial-blob). When you import the collection, modify the headers and URL to use your service name and API key. The purpose of this sample is to demonstrate how creating a cognitive search pipeline adds new information and structure to unstructured files.

## Contents

| File/folder | Description |
|-------------|-------------|
| `cog-search-demo REST tutorial.postman_collection.json`       | Import into Postman |
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
1. Start Postman and import cog-search-demo REST tutorial.postman_collection.json
1. For each request, update the Header to use the admin api-key of your service, which you can obtain from the portal.
1. Next, update the URL of each request to use the name of your search service.
1. Send each request to the service.

## Next steps

You can learn more about Azure Cognitive Search on the [official documentation site](https://docs.microsoft.com/azure/search).