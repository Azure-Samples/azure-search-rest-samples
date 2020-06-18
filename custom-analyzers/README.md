---
page_type: sample
languages:
  - rest
name: Custom Analyzer Tutorial - Postman
description: |
  Learn how to create a custom analyzer in Azure Cognitive Search to intuitively search across phone numbers or other content.
products:
  - azure
  - azure-cognitive-search
urlFragment: custom-analyzer-tutorial
---

# Create a custom analyzer in Azure Cognitive Search using REST APIs and Postman

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

This Postman collection creates a basic search index and builds an analyzer designed for searching phone numbers. The collection and corresponding tutorial walk through the process of testing sample searches, testing how those searches are analyzed, and building an analyzer to intuitively search phone numbers.

This collection is featured in the [Tutorial: Create a custom analyzer using REST APIs](https://docs.microsoft.com/azure/search/tutorial-create-custom-analyzer). When you import the collection, modify the headers and URL to use your service name and API key.

## Contents

| File/folder | Description |
|-------------|-------------|
| `custom-analyzer-tutorial.postman_collection.json`       | Import into Postman |
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

1. Start Postman and import `custom-analyzer-tutorial.postman_collection.json`.
1. For each request, update the Header to use the admin api-key of your service, which you can obtain from the portal.
1. Next, update the URL of each request to use the name of your search service.
1. Send each request to the service.

## Next steps

You can learn more about Azure Cognitive Search on the [official documentation site](https://docs.microsoft.com/azure/search).