---
page_type: sample
languages:
  - rest
name: Index encrypted blob files using REST - Postman
description: |
  To be used with the tutorial for how to index encrypted Azure Blob Storage files into Azure Cognitive Search
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-encrypted-blob-files
---

#  Indexing encrypted Blob files in Azure Cognitive Search using REST APIs and Postman

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

This [Postman](https://www.getpostman.com/) collection uses the Azure Cognitive Search REST APIs to create the resources necessary to be able to index files that have been encrypted in Azure Blob Storage: a data source, an index, a skillset with select skills, and an indexer with a specific configuration. Requests are provided in the V2 collection format, which you can import and then modify for connections to your search service.

The purpose of this sample is to demonstrate how, if you have an existing Azure Storage account with encrypted blobs, you can successfully index them into Azure Cognitive Search.

## Contents

| File/folder | Description |
|-------------|-------------|
| `Index encrypted Blob files.postman_collection.json`       | Import into Postman |
| `CONTRIBUTING.md` | Guidelines for contributing to the sample. |
| `README.md` | This README file. |
| `LICENSE.md`   | The license for the sample. |

## Prerequisites

- [Postman Desktop app](https://www.getpostman.com/)
- [Azure Cognitive Search service](https://docs.microsoft.com/azure/search/search-create-service-portal)
- [DecryptBlobFile Azure Function power skill](https://github.com/Azure-Samples/azure-search-power-skills/tree/master/Utils/DecryptBlobFile)

## Setup

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.

### Running tutorial

Please see the documentation [How to index encrypted blobs using blob indexers and skillsets in Azure Cognitive Search](https://docs.microsoft.com/azure/search/search-howto-index-encrypted-blobs) for instructions on how to use this Postman collection.

## Next steps

You can learn more about Azure Cognitive Search on the [official documentation site](https://docs.microsoft.com/azure/search).
