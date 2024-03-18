# Custom Entity Lookup skill in Azure AI Search

**Important**:  This sample is currently archived while we update the steps.

This sample demonstrates one of the entity-related built-in skills in Azure AI Search, [Custom Entity Lookup](https://docs.microsoft.com/azure/search/cognitive-search-skill-custom-entity-lookup).

In contrast with [Entity Recognition](https://docs.microsoft.com/azure/search/cognitive-search-skill-entity-recognition-v3), which finds whatever the public model tells it find, [Custom Entity Lookup](https://docs.microsoft.com/azure/search/cognitive-search-skill-custom-entity-lookup) finds whatever you tell it to find. You can provide the skill with a simple list of entities, or you can further define those entities by type and subtype. You can also assign aliases for variations of an entity name. In a search solution, custom entities are useful for filters, facets, and sorting.

In this sample, you'll learn the following techniques:

+ Create a [custom entity definition](https://docs.microsoft.com/azure/search/cognitive-search-skill-custom-entity-lookup#custom-entity-definition-format) that defines the entities
+ Create a skillset that includes the [Custom Entity Lookup skill](https://docs.microsoft.com/azure/search/cognitive-search-skill-custom-entity-lookup)
+ Create a search index that models the complex types of Custom Entity Lookup skill output
+ Create a search indexer that specifies the output field mappings

## Prerequisites

+ Azure AI Search (free or billable version)
+ Azure Storage 
+ Sample data and sample custom entity definition, both uploaded to blob containers in Azure Storage

To authenticate to your Azure services, you'll need the API key for Azure AI Search and a full access connection string for Azure Storage. A full access connection string incudes an account key used for accessing your content. If you're unfamiliar with setting up REST calls, see [Quickstart: Text search using REST](https://docs.microsoft.com/azure/search/search-get-started-rest).

## Upload sample data and get a storage connecton string

The sample data used for this example consists of famous speeches in PDF file format, uploaded to a blob container in Azure Storage. These files can be found at [Azure-Samples/azure-search-sample-data/famous-speeches-pdf](https://github.com/Azure-Samples/azure-search-sample-data/tree/main/famous-speeches-pdf). You can upload these files to a blob container in Azure Storage and then reference the container and connection string in your indexer data source.

The custom entity definition is an external JSON file with entities that match the sample data. This file is named "custom-entities-famous-speeches.json" and is located in the same folder as this readme. You can upload this file to Azure Storage and then reference its fully-qualified path name in your skillset.

1. In Azure Storage, create a container named "famous-speeches" and upload [Azure-Samples/azure-search-sample-data/famous-speeches-pdf](https://github.com/Azure-Samples/azure-search-sample-data/tree/main/famous-speeches-pdf).

1. Create a second container named "famous-speeches-custom-entities" and upload [Azure-Samples/azure-search-rest-samples/custom-entity-lookup-skill/custom-entities-famous-speeches.json](https://github.com/Azure-Samples/azure-search-rest-samples/custom-entity-lookup-skill/custom-entities-famous-speeches.json).

1. From **Access keys** on the left, copy a connection string.

## Create a custom entity definition

You can provide the custom entity definition as an external CSV or JSON file, or as an inline definition which is useful for proof-of-concept testing and small workloads. Since you're more likely to use an external file, this sample includes a JSON file with entity mappings that align to the sample data. This custom entity definition is simple. For more advanced scenarios, see [Custom entity definition format](https://docs.microsoft.com/azure/search/cognitive-search-skill-custom-entity-lookup#custom-entity-definition-format).

If you are running the sample, upload this JSON file to its own blob container in Azure Storage.

1. Identify entities of interest. Because this data set consists of famous American civic speeches, the entities include themes and concepts that are common to this genre.

   + equal (alias "equality")
   + founding fathers (alias "fathers")
   + freedom (alias "liberty")
   + god
   + justice
   + nation (alias "country")
   + revolution
   + rights

1. Save the following as a JSON file and then upload it to a blob container in Azure Storage. 

  ```
  [ 
      { 
          "name" : "equality",
          "aliases" : [ 
              { "text" : "equal", "caseSensitive" : false }
          ]
      }, 
      { 
          "name" : "founding fathers",
          "aliases" : [ 
              { "text" : "fathers", "caseSensitive" : false }
          ]
      }, 
      { 
          "name" : "freedom",
          "aliases" : [ 
              { "text" : "liberty", "caseSensitive" : false }
          ]
      },
      { 
          "name" : "god"
      }, 
      { 
          "name" : "justice"
      }, 
      { 
          "name" : "nation",
          "aliases" : [ 
              { "text" : "country", "caseSensitive" : false }
          ]
      },
      { 
          "name" : "revolution"
      }, 
      { 
          "name" : "rights"
      }
  ]
  ```

1. Get the blob URL. Select the blob, right-select **Properties**. The URL is the first property. Select the copy button to copy the URL.

## Set up the variables

In the .rest file, paste in the values used to run the commands.

1. Open skill-example-custom-entity-lookup.rest in Visual Studio Code.

1. In the variables at the top, paste in the values you collected earlier:

```http

```

## Send the rest calls

After you provide the variables, select **Send request** on each command:

+ Create data source
+ Create skillset
+ Create index
+ Create indexer

The skillset specifies a combination of Custom Entity Lookup skill and Entity Recognition. The skill definition includes a pointer to the blob container that stores the custom entity definition.

The index includes blob metadata, fields for entity recognition output, and fields for custom entity lookup.


The indexer is where you configure execution settings. By default, creating the indexer also runs it on the search service. Output field mappings are used to route enriched content, such as predefined and custom entities, to fields in a search index.

## Check results

You can switch to the Azure portal and use Search Explorer to query results, or run the following GET verbs to view indexer status, followed by a basic query once indexer execution is finished to view the content. Indexer and enrichment processing takes a few minutes to complete.

This command gets indexer status:

```http
### Get indexer status
GET {{baseUrl}}/indexers/famous-speeches-idxr/status?api-version=2023-11-01
   api-key: {{apiKey}}
```

You can query the search index as soon as the first document is processed. Although you can use GET, using POST allows you to set query parameters in the body of the request, which is easier to modify and re-run.

```http
### Run a search query
POST {{baseUrl}}/indexes/famous-speeches-idx/docs/search?api-version=2023-11-01
  Content-Type: application/json
  api-key: {{apiKey}}

    {
        "search": "*",
        "queryType": "simple",
        "select": "entities, people, organizations, locations",
        "searchFields": "",
        "filter": "",
        "orderby": "",
        "count": true
    }
```

The custom entity lookup skill does not aggregate or consolidate entity instances within a document. If a document has multiples of the same entity, each occurrence will be listed in the results, along with its match details, which might be more verbose than what you're expecting.

Here are the results for the Gettysburg Address, where the entity "nation" occurs five times in the document.

```
{
    "@odata.count": 4,
    "value": [
        {
            "@search.score": 1.0,
            "people": [
                "Abraham Lincoln"
            ],
            "organizations": [
                "Lit2Go"
            ],
            "locations": [
                "Gettysburg",
                "National Cemetery",
                "Pennsylvania",
                "continent",
                "battle-field"
            ],
            "entities": [
                {
                    "name": "founding fathers",
                    "id": null,
                    "description": null,
                    "type": null,
                    "subtype": null,
                    "matches": [
                        {
                            "text": "fathers",
                            "offset": 199,
                            "length": 7,
                            "matchDistance": 0.0
                        }
                    ]
                },
                {
                    "name": "nation",
                    "id": null,
                    "description": null,
                    "type": null,
                    "subtype": null,
                    "matches": [
                        {
                            "text": "nation",
                            "offset": 246,
                            "length": 6,
                            "matchDistance": 0.0
                        },
                        {
                            "text": "nation",
                            "offset": 406,
                            "length": 6,
                            "matchDistance": 0.0
                        },
                        {
                            "text": "nation",
                            "offset": 421,
                            "length": 6,
                            "matchDistance": 0.0
                        },
                        {
                            "text": "nation",
                            "offset": 649,
                            "length": 6,
                            "matchDistance": 0.0
                        },
                        {
                            "text": "nation",
                            "offset": 1494,
                            "length": 6,
                            "matchDistance": 0.0
                        }
                    ]
                },
                {
                    "name": "freedom",
                    "id": null,
                    "description": null,
                    "type": null,
                    "subtype": null,
                    "matches": [
                        {
                            "text": "Liberty",
                            "offset": 267,
                            "length": 7,
                            "matchDistance": 0.0
                        },
                        {
                            "text": "freedom",
                            "offset": 1540,
                            "length": 7,
                            "matchDistance": 0.0
                        }
                    ]
                },
                {
                    "name": "equality",
                    "id": null,
                    "description": null,
                    "type": null,
                    "subtype": null,
                    "matches": [
                        {
                            "text": "equal",
                            "offset": 335,
                            "length": 5,
                            "matchDistance": 0.0
                        }
                    ]
                },
                {
                    "name": "god",
                    "id": null,
                    "description": null,
                    "type": null,
                    "subtype": null,
                    "matches": [
                        {
                            "text": "God",
                            "offset": 1508,
                            "length": 3,
                            "matchDistance": 0.0
                        }
                    ]
                }
            ]
        },
```

## Next steps

Remember to delete any Azure services and data that you're no longer using. If you'd like to continue with other skills or features, see the [official docs](https://docs.microsoft.com/azure/search/).
