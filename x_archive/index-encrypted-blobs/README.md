# Index encrypted Blob files in Azure AI Search using REST APIs

**Important**:  This sample is currently archived while we update the steps.

This example uses the Azure AI Search REST APIs to create the resources necessary to be able to index files that have been encrypted in Azure Blob Storage: a data source, an index, a skillset with select skills, and an indexer with a specific configuration. 

The purpose of this sample is to demonstrate how, if you have an existing Azure Storage account with encrypted blobs, you can successfully index them into Azure AI Search.

## Prerequisites

+ [Visual Studio Code](https://code.visualstudio.com/download) with a [REST client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

+ [Azure AI Search](https://learn.microsoft.com/azure/search/). [Create](https://learn.microsoft.com//azure/search/search-create-service-portal) or [find an existing Azure AI Search resource](https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Search%2FsearchServices) under your current subscription.

+ [Azure Storage account](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal)

+ [DecryptBlobFile Azure Function power skill](https://github.com/Azure-Samples/azure-search-power-skills/tree/master/Utils/DecryptBlobFile)

## Setup

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.

### Running tutorial

Please see the documentation [How to index encrypted blobs using blob indexers and skillsets in Azure AI Search](https://docs.microsoft.com/azure/search/search-howto-index-encrypted-blobs) for instructions.

## Next steps

You can learn more about Azure AI Search on the [official documentation site](https://docs.microsoft.com/azure/search).
