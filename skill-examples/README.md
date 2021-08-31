---
page_type: sample
languages:
  - rest
name: "Skill Examples - Postman"
description: |
  Each collection includes a skillset definition, index, indexer, and data source so that you can see how parameters and nodes in an enrichment tree are referenced in related objects.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-skill-example
---

# End-to-end skill examples for Azure Cognitive Search using REST APIs and Postman

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

Each collection includes all of the objects required to move sample data from the original data source (usually Azure Blob Storage) to a searchable index on your search service.

The skillsets are simple, usually one or two skills, to make it easier to follow the parameter and node references across indexer output field mappings and the field definitions in an index.

After you import each collection into Postman, edit the collection variables to use your search service and an admin API key.

## Contents

| File        | Description |
|-------------|-------------|
| `Skill example - Entity Linking.postman_collection.json` | Creates a data source, skillset, index, and indexer with output field mappings. For data, this collection assumes a blob container holding the first 10 "text-only" PDFs of the [NASA e-book](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/nasa-e-book) sample data files. |
| `Skill example - Entity Linking with renamed fields.postman_collection.json` | This version of the previous example includes a Shaper skill that renames skill outputs to values you might want to use in an index. |
| `Skill example - Entity Recognition.postman_collection.json` | Creates a data source, skillset, index, and indexer with output field mappings. For data, this collection assumes a blob container holding the first 10 "text-only" PDFs of the [NASA e-book](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/nasa-e-book) sample data files. |
| `Skill example - Image Analysis.postman_collection.json` | Creates a data source, skillset, index, and indexer with output field mappings. For data, this collection assumes a blob container holding [photos of buildings and landmarks](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/unsplash-images/jpg-landmarks). |
| `Skill example - OCR.postman_collection.json` | Creates a data source, skillset, index, and indexer with output field mappings. For data, this collection assumes a blob container holding [photos of signs](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/unsplash-images/jpg-signs). |
| `Skill example - OCR with renamed fields.postman_collection.json` | This version of the previous example includes a Shaper skill that renames skill outputs to values you might want to use in an index. |
| `Skill example - Text Translation and Language Detection.postman_collection.json` | Creates a data source, skillset, index, and indexer with output field mappings. For data, this collection assumes a blob container holding Word doc files containing descriptions of [Spanish museums in French and Spanish](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/spanish-museums). |
| `.gitignore` | Defines what to ignore at commit time. |
| `CONTRIBUTING.md` | Guidelines for contributing to the sample. |
| `README.md` | This README file. |
| `LICENSE`   | The license for the sample. |

## Prerequisites

- [Postman Desktop app](https://www.getpostman.com/)
- [Azure Cognitive Search service](https://docs.microsoft.com/azure/search/search-create-service-portal)
- [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal)
- [Sample data (uploaded to blob containers in Blob Storage)](https://github.com/Azure-Samples/azure-search-sample-data)

## Setup

1. Clone or download this sample repository.

1. Extract contents if the download is a zip file. Make sure the files are read-write.

1. Start Postman.

1. Under **Files** > **New**, select a collection to import.

1. After the collection is imported, expand the actions list (**...**).

1. Click **Edit**.

1. Replace <`SEARCH-SERVICE-NAME`> with the name of your search service (for example, if the endpoint is https://mydemo.search.windows.net, then the service name is "mydemo").

1. Replace <`ADMIN-API-KEY`> with either the primary or secondary key of your search service. 

   Admin keys are necessary if you are creating or deleting objects. You can get admin keys from the portal page for your service.

Once you have updated the variables, you can run any request in the collection. 

## Next steps

You can learn more about Azure Cognitive Search on the [official documentation site](https://docs.microsoft.com/azure/search).
