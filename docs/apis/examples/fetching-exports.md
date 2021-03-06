# Fetching Exports

To fetch the exports you first need to fetch the MapPlan. You can do  this by using the `node` query. For details see the [Fetching a Single Object](/apis/examples/fetching-a-single-object.md) section.

[Click here to view this example in the API explorer, substitute your own plan_id to execute the query.](https://www.dronedeploy.com/graphql?operationName=null&query=query%7B%0A%20%20node%28id%3A%22MapPlan%3A5a0de0835f1e08eaabc732bd%22%29%7B%0A%20%20%20%20...%20on%20MapPlan%7B%0A%20%20%20%20%20%20exports%28first%3A5%29%7B%0A%20%20%20%20%20%20%20%20edges%20%7B%0A%20%20%20%20%20%20%20%20%20%20node%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20id%0A%20%20%20%20%20%20%20%20%20%20%20%20user%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20username%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20parameters%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20projection%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20merge%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20contourInterval%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20fileFormat%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20resolution%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20status%0A%20%20%20%20%20%20%20%20%20%20%20%20dateCreation%0A%20%20%20%20%20%20%20%20%20%20%20%20downloadPath%0A%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%20%20%7D%0A%7D%0A)

```
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

```
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

### Checking the status of an Export

If you want to keep checking back on the status of a given export you can use the same query shown in Fetching a Single Object to get it.

```
query GetExport{
  node(id:"Export:5ab165f348273300019b14a3"){
    ... on Export{
      status
      downloadPath
    }
  }
}
```





