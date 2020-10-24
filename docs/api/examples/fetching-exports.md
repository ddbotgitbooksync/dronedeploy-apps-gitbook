# Fetching Exports

To fetch the exports you first need to fetch the MapPlan. You can do this by using the `node` query. For details see the [Fetching a Single Object](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/c927048f33aac44c8e61d230dc43194aca71784c/apis/examples/fetching-a-single-object.md) section.

[Click here to view this example in the API explorer, substitute your own plan\_id to execute the query.](https://www.dronedeploy.com/graphql?operationName=null&query=query{
%20%20node%28id%3A"MapPlan%3A5a0de0835f1e08eaabc732bd"%29{
%20%20%20%20...%20on%20MapPlan{
%20%20%20%20%20%20exports%28first%3A5%29{
%20%20%20%20%20%20%20%20edges%20{
%20%20%20%20%20%20%20%20%20%20node%20{
%20%20%20%20%20%20%20%20%20%20%20%20id
%20%20%20%20%20%20%20%20%20%20%20%20user{
%20%20%20%20%20%20%20%20%20%20%20%20%20%20username
%20%20%20%20%20%20%20%20%20%20%20%20}
%20%20%20%20%20%20%20%20%20%20%20%20parameters%20{
%20%20%20%20%20%20%20%20%20%20%20%20%20%20projection
%20%20%20%20%20%20%20%20%20%20%20%20%20%20merge
%20%20%20%20%20%20%20%20%20%20%20%20%20%20contourInterval
%20%20%20%20%20%20%20%20%20%20%20%20%20%20fileFormat
%20%20%20%20%20%20%20%20%20%20%20%20%20%20resolution
%20%20%20%20%20%20%20%20%20%20%20%20}
%20%20%20%20%20%20%20%20%20%20%20%20status
%20%20%20%20%20%20%20%20%20%20%20%20dateCreation
%20%20%20%20%20%20%20%20%20%20%20%20downloadPath
%20%20%20%20%20%20%20%20%20%20}
%20%20%20%20%20%20%20%20}
%20%20%20%20%20%20}
%20%20%20%20}
%20%20}
}
)

```text
query GetExports{
  node(id:"MapPlan:5a0de0835f1e08eaabc732bd"){
    ... on MapPlan{
      exports(first:5){
        edges {
          node {
            id
            user{
              username
            }
            parameters {
              projection
              merge
              contourInterval
              fileFormat
              resolution
            }
            status
            dateCreation
            downloadPath
          }
        }
      }
    }
  }
}
```

This returns the data:

```text
{
  "data": {
    "node": {
      "exports": {
        "edges": [
          {
            "node": {
              "id": "Export:5ab165f348273300019b14a3",
              "user": {
                "username": "example@dronedeploy.com"
              },
              "parameters": {
                "projection": 3857,
                "merge": true,
                "contourInterval": null,
                "fileFormat": "GEOTIFF",
                "resolution": 0
              },
              "status": "PROCESSING",
              "dateCreation": "2018-03-20T19:50:11.523000+00:00",
              "downloadPath": null
            }
          }
        ]
      }
    }
  }
}
```

## Checking the status of an Export

If you want to keep checking back on the status of a given export you can use the same query shown in Fetching a Single Object to get it.

```text
query GetExport{
  node(id:"Export:5ab165f348273300019b14a3"){
    ... on Export{
      status
      downloadPath
    }
  }
}
```

