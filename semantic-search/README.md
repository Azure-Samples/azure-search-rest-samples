---
page_type: sample
languages:
  - rest
name: Semantic Search - Postman
description: |
  Learn how to create an index with a semantic configuration and issue queries with semantic search
products:
  - azure
  - azure-cognitive-search
urlFragment: semantic-search-postman
---

# Create an index with a semantic configuration and issue queries with semantic search

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

This Postman collection creates a basic search index with a semantic configuration, loads data into the index, and then creates a semantic query.

This collection is mentioned in the [Create a query that invokes semantic ranking and returns semantic captions](https://docs.microsoft.com/azure/search/semantic-how-to-query-request). When you import the collection, modify the headers and URL to use your service name and API key.

## Contents

| File/folder | Description |
|-------------|-------------|
| `semantic-search.postman_collection.json`       | Import into Postman |
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

1. Start Postman and import `semantic-search.postman_collection.json`.
1. For each request, update the Header to use the admin api-key of your service, which you can obtain from the portal.
1. Next, update the URL of each request to use the name of your search service.
1. Send each request to the service.

## Next steps

You can learn more about Azure Cognitive Search on the [official documentation site](https://docs.microsoft.com/azure/search).