---
page_type: sample
languages:
  - rest
name: "Skill Examples - REST"
description: |
  Examples includes a skillset definition, index, indexer, and data source so that you can see how parameters and nodes in an enrichment tree are referenced in related objects.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-skill-example
---

# End-to-end skill examples for Azure AI Search using REST APIs

Each example is standalone, providing all of the objects required to move sample data from the original data source (usually Azure Blob Storage), through an enrichment pipeline, to a searchable index on your search service.

The skillsets are simple, usually one or two skills, to make it easier to follow the parameter and node references across indexer output field mappings and the field definitions in an index.

You need a REST client for these examples. We recommend [Visual Studio Code](https://code.visualstudio.com/download) with a [REST client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

## Contents

| File        | Description |
|-------------|-------------|
| `skill-examples\skill-example-entity-linking.rest` | Creates a data source, skillset, index, and indexer with output field mappings. For data, this collection assumes a blob container holding the first 10 "text-only" PDFs of the [NASA e-book](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/nasa-e-book) sample data files. |
| `Skill example - Entity Linking with renamed fields.postman_collection.json` | This version of the previous example includes a Shaper skill that renames skill outputs to values you might want to use in an index. |
| `skill-examples\skill-example-entity-recognition.rest` | Creates a data source, skillset, index, and indexer with output field mappings. For data, this collection assumes a blob container holding the first 10 "text-only" PDFs of the [NASA e-book](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/nasa-e-book) sample data files. |
| `skill-examples\skill-example-image-analysis.rest` | Creates a data source, skillset, index, and indexer with output field mappings. For data, this collection assumes a blob container holding [photos of buildings and landmarks](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/unsplash-images/jpg-landmarks). |
| `skill-examples\skill-example-ocr.rest` | Creates a data source, skillset, index, and indexer with output field mappings. For data, this collection assumes a blob container holding [photos of signs](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/unsplash-images/jpg-signs). |
| `skill-examples\skill-example-ocr-renamed-fields.rest` | This version of the previous example includes a Shaper skill that renames skill outputs to values you might want to use in an index. |
| `skill-examples\skill-example-text-translation-language-detection.rest` | Creates a data source, skillset, index, and indexer with output field mappings. For data, this collection assumes a blob container holding Word doc files containing descriptions of [Spanish museums in French and Spanish](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/spanish-museums). |

## Prerequisites

- [Azure AI Search service](https://docs.microsoft.com/azure/search/search-create-service-portal)
- [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal)
- [Sample data (uploaded to blob containers in Blob Storage)](https://github.com/Azure-Samples/azure-search-sample-data)

## Set up the sample

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.

## Run the code

1. Start Visual Studio Code and open a `.rest` file.
1. Provide a valid search service name, search service admin API key, Azure Storage connection string, and the blob container name in the variables.
1. **Save** the file.
1. Send each request to the service.

## Next steps

You can learn more about Azure AI Search on the [official documentation site](https://docs.microsoft.com/azure/search).
