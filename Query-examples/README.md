---
page_type: sample
languages:
  - rest
name: "Query Examples - Postman"
description: |
  Try out Azure Cognitive Search queries - autocomplete, suggestions, simple queries, fuzzy search, proximity search, wildcard search, RegEx queries, and more.
products:
  - azure
  - azure-cognitive-search
urlFragment: rest-api-query-examples
---

# Query examples for Azure Cognitive Search using REST APIs and Postman

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

Demonstrates using Postman and the Azure Cognitive Search REST APIs to query an index. The collections in this repository are intended for import into Postman, an API client useful for making REST calls against a service.

## Contents

| File/folder | Description |
|-------------|-------------|
| `Query examples - autocomplete, suggestions` | Demonstrates suggesters, autocomplete, and suggested results. Demo data consists of several XBox game titles and descriptions. The purpose of this example is a hands on experience with the APIs. The API client does not support a true search-as-you-type experience, but you can simulate autocomplete by clicking **SEND** after each character input (for example, `"m" <send>`, `"mi" <send>`,`"min" <send>`, and so forth. |
| `Query examples - full Lucene syntax` | Demonstrates query forms enabled by the full syntax, including wildcard (infix and suffix), regular expressions, proximity search, field-boosted search. Demo data is a NYCJobs data hosted on a read-only index. |
| `Query examples - partial terms and special characters` | Partial term queries are composed of parts of a term instead of a whole term. Queries for URLs, phone numbers, postal codes, and hyphenated strings introduce tokenization requirements, which are addressed through analyzers assigned to fields. Demo data for this collection is composed of strings in various patterns and configurations.|
| `Query examples - simple syntax` | Demonstrates the boolean operators, precedence, and escape rules. To demonstrate escape rules, the demo data set is similar to that of partial terms and special characters.|
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

1. Start Postman.

1. Under **Files** > **New**, select a collection to import.

1. After the collection is imported, expand the actions list (**...**).

1. Click **Edit**.

1. Replace <`YOUR-SEARCH-SERVICE`> with the name of your search service (for example, if the endpoint is https://mydemo.search.windows.net, then the service name is "mydemo").

1. Replace <`YOUR-ADMIN-API-KEY`> with either the primary or secondary key of your search service. 

   Admin keys are necessary if you are creating or deleting objects. All collections, with the exception of the full Lucene syntax that uses a hosted index, require the creation of an index. You can get admin keys from the portal page for your service.

Once you have updated the variables, you can run any request in the collection. 

## Next steps

You can learn more about Azure Cognitive Search on the [official documentation site](https://docs.microsoft.com/azure/search).
