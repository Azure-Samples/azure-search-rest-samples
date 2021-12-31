---
page_type: sample
languages:
  - rest
name: Debug skillsets in Azure Cognitive Search
description: |
  Learn how the Debug Sessions visual editor can help you fix enrichment pipeline issues in Azure Cognitive Search. This collection creates a skillset with invalid fields and missing data, easily fixed in a debug session.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-debug-sessions
---

# Fix skillset issues using Debug Sessions in Azure Cognitive Search 

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

This [Postman](https://www.getpostman.com/) collection uses the Azure Cognitive Search REST APIs to create an enrichment pipeline with warnings you can fix in the Debug Sessions tool in Azure portal. Requests are provided in the V2 collection format, which you can import and then modify for connections to your search service.

This readme also explains how to set up the clinical trials data used in this collection.

## Contents

| File/folder | Description |
|-------------|-------------|
| `Debug-sessions.postman_collection.json`       | Import into Postman |
| `CONTRIBUTING.md` | Guidelines for contributing to the sample. |
| `README.md` | This README file. |
| `LICENSE.md`   | The license for the sample. |

## Prerequisites

- [Postman Desktop app](https://www.getpostman.com/)
- [Azure Cognitive Search service](https://docs.microsoft.com/azure/search/search-create-service-portal)
- [Azure Storage account](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal)
- [Clinical Trials Data (19 documents)](https://github.com/Azure-Samples/azure-search-sample-data/tree/master/clinical-trials-pdf-19)

## Set up the data

1. Download the clinical trials data set.

1. In Azure portal, in Azure Storage, [create a Blob container](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal) and upload the 19 documents.

1. Make a note of the blob container name.

## Get connection information

Collect the connection information you'll need to provide on the requests. In a later step, you'll paste these values into variables on the collection.

1. Still in Azure portal, in Azure Storage, select **Access keys** on the left. Copy one of the connection strings. It should be in this format: `DefaultEndpointsProtocol=https;AccountName=<YOUR-STORAGE-ACCOUNT>;AccountKey=<YOUR-ACCESS-KEY>;`

1. Paste the connection string into Notepad and remove the last segment: `EndpointSuffix=core.windows.net`. When deleting part of the string, be careful to preserve the trailing semi-colon after the key.

1. Back in the portal, go to the Azure Cognitive Search **Overview** page of your search service.

1. Get the name of the service (for example, given an endpoint of `https://demo-svc.search.windows.net`, the service name is `demo-svc`).  Paste the search service name into Notepad.

1. Select **Keys** on the left and copy one of admin keys. Paste it into Notepad.

## Set up the Postman collection

1. Clone or download this sample repository.

1. Extract contents if the download is a zip file. Make sure the files are read-write.

1. Start Postman and select **Import** to load the Debug-sessions Postman collection.

1. After importing the collection, expand the (`...`) action list and select **Edit**.

1. Select **Variables** and enter the values you collected earlier:

   + In **searchService**, enter the name of your search service.
   + In **apiKey**, enter the admin API key of your search service.
   + In **storageConnectionString**, enter the connection string for your Azure Storage account.
   + In **blobContainer**, enter the name of the blob container that stores the clinical trials documents.

## Send the requests

After you have finished adding the variable, you can run each request in turn, with no further modification. 

1. Start with **CreateDataSource**, click **Send** to submit the request to Azure Cognitive Search. This request creates a data source object that specifies the connection to the Blob container.

1. Continue on to **CreateSkillset**. This request creates, but does not run, a skillset definition on the search service.

1. Send the **CreateIndex** request to create the index definition. An enrichment pipeline sends output to a searchable index. The index stores the searchable content created by the pipeline.

1. The **CreateIndexer** request executes the pipeline. Data movement occurs in this step: loading PDFs from the blob container, cracking the PDFs, formulating requests for AI processing, composing the enriched documents which include extracted and created data, and outputting the content to a search index.

You have now created all of the objects necessary for using Debug sessions. This collection excludes monitoring and verification steps. You'll do that in the portal with Debug sessions tutorial. 

## Next steps

By design, the indexer produces warnings and omits data. To learn how to find and fix these issues in Debug sessions, go to [Tutorial: Diagnose, repair, and commit changes to your skillset](https://docs.microsoft.com/azure/search/cognitive-search-tutorial-debug-sessions) for the next steps.