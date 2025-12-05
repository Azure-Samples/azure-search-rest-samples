---
page_type: sample
languages:
  - rest
name: ACL quickstart
description: |
  Learn how to configure basic access-control examples for Azure AI Search using REST.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-acl
---

# Quickstart: ACL in Azure AI Search using REST APIs

This sample demonstrates how to create an index that uses permission filters and how to query documents with and without query-source authorization. Requests are provided in the `acl.http` file, which you can open and modify with your own connection information.

This sample is featured in [Query-time ACL and RBAC enforcement in Azure AI Search](https://learn.microsoft.com/azure/search/search-query-access-control-rbac-enforcement).

## Prerequisites

+ An [Azure AI Search service](https://learn.microsoft.com/azure/search/search-create-service-portal) on any pricing tier.

+ An account with access to [Microsoft Graph](https://learn.microsoft.com/graph/api/resources/groups-overview?view=graph-rest-1.0&tabs=http) if you want to send Graph API requests.

+ [Visual Studio Code](https://code.visualstudio.com/download) with the [REST Client extension](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

## Set up the sample

1. Clone or download this sample repository.

1. If the download is a ZIP file, extract its contents. Make sure the files are read-write.

1. Configure access to the Azure resources and get their connection information.

## Run the code

1. Open the `acl.http` file in Visual Studio Code.

1. Replace the placeholder variables with valid values.

1. Save the file.

1. Send each request to Azure AI Search or Microsoft Graph.

## Next step

You can learn more about Azure AI Search on the [official documentation site](https://learn.microsoft.com/azure/search).
