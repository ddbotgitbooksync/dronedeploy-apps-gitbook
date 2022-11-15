# Fetching all Plans for your Organization

## Fetching all Plans for your Organization

Below is the query to fetch all the plans, with their name, geometry, location and the date they were created. Since this is a paged API you also need to fetch the `pageInfo`, [see Pagination](../pagination.md) for more details.

```
query GetPlans{
  viewer{
    organization{
      plans(first:50){
        pageInfo{
          hasNextPage
          endCursor
        }
        edges{
          cursor
          node{
            name
            geometry{
              lat
              lng
            }
            location {
              lat
              lng
            }
            dateCreation
          }
        }
      }
    }
  }
}
```

You can try this query out yourself using [the API explorer here.](https://www.dronedeploy.com/graphql?query=query%20GetPlans%7B%20viewer%7B%20organization%7B%20plans\(first%3A50\)%7B%20pageInfo%7B%20hasNextPage%20endCursor%20%7D%20edges%7B%20cursor%20node%7B%20name%20geometry%7B%20lat%20lng%20%7D%20location%20%7B%20lat%20lng%20%7D%20dateCreation%20%7D%20%7D%20%7D%20%7D%20%7D%20%7D\&operationName=GetPlans)

The top level query `viewer` is the context for the currently logged in user. From this you fetch the `organization` object and the first 50 of the plans associated with that. If you have less than 50 plans you are done. If you have more example you will get a response like this.

```javascript
{
  "data": {
    "viewer": {
      "organization": {
        "plans": {
          "pageInfo": {
            "hasNextPage": true,
            "endCursor": "YXJyYXljb25uZWN0aW9uOjI="
          },
          "edges": [
            ...  // Data removed for the sake of brevity
          ]
        }
      }
    }
  }
}
```

As you can see in the `pageInfo` section `hasNextPage` is True so you know you need to fetch the next page of data. To do this simply modify your query to set the `after` paging parameter to the `endCursor` from the `pageInfo`:

```
query GetPlans{
  viewer{
    organization{
      plans(first:50, after:"YXJyYXljb25uZWN0aW9uOjI="){
        pageInfo{
          hasNextPage
          endCursor
        }
        edges{
          cursor
          node{
            name
            geometry{
              lat
              lng
            }
            location {
              lat
              lng
            }
            dateCreation
          }
        }
      }
    }
  }
}
```

## More Detail

If you look through the schema the `plans` query returns type `Plan`. This is an interface for the common fields across all types of plans. There are more specific types of Plans, specifically `MapPlan` which includes more data such as exports. To fetch these extra fields you need to use an [Inline Fragment](https://graphql.org/learn/queries/#fragments).

[This query:](https://www.dronedeploy.com/graphql?query=query%20GetPlans%7B%20viewer%7B%20organization%7B%20plans\(first%3A50\)%7B%20edges%7B%20node%7B%20name%20...%20on%20MapPlan%7B%20status%20%20%0A%7D%20%7D%20%7D%20pageInfo%7B%20hasNextPage%20endCursor%20%7D%20%7D%20%7D%20%7D%20%7D\&operationName=GetPlans)

```
query GetPlans{
  viewer{
    organization{
      plans(first:50){
        edges{
          node{
            id
            name
            ... on MapPlan{
              status              
            }
          }
        }
        pageInfo{
          hasNextPage
          endCursor
        }
      }
    }
  }
}
```

This specifies that you are looking for the `id` and `name` of all plans, but for objects of type `MapPlan` you want the `status` of the processing as well.
