# Creating an Export

Our APIs are not just for viewing data, you can also create data with [mutations.](http://graphql.org/learn/queries/#mutations)

For these examples you will need to substitute your own PlanIDs.

The easiest way to try these APIs is to use the [API Explorer](https://www.dronedeploy.com/graphql?operationName=null&query=mutation{
%20%20createExport%28input%3A{planId%3A%20"MapPlan%3A5a0ddee5a6b7d90aecdc2f1d"%2C%20parameters%3A{layer%3AORTHOMOSAIC}}%29{
%20%20%20%20export{
%20%20%20%20%20%20id
%20%20%20%20}
%20%20}
}
&variables=). This has useful features like autocomplete \(ctrl+space\) and query/input validation.

```text
mutation{
  createExport(input:{planId: "MapPlan:5a0ddee5a6b7d90aecdc2f1d", parameters:{layer:ORTHOMOSAIC}}){
    export{
      id
    }
  }
}
```

Here the createExport mutation takes an input of `planId` and `parameters`. In parameters only the `layer` is required.

This will create the export and then query for the exports id in the response:

```text
{
  "data": {
    "createExport": {
      "export": {
        "id": "Export:5ab169ed8904ec000136eac9"
      }
    }
  }
}
```

You can then use the steps in [Fetching Exports](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/c927048f33aac44c8e61d230dc43194aca71784c/apis/examples/fetching-exports.md) to check on the status of that export.

## Using Variables

As the input gets more complex you will want to use GraphQL variables. For some background information on Variables in Mutations, [see here](http://graphql.org/learn/queries/#variables).

To take the query above and use variables you need to do 3 things:

1. Define the variable in the mutation signature:

   > `mutation($input:CreateExportInput!){`

2. Use the defined variable in the mutation:

   > `createExport(input:$input){`

3. Define the value of the variable in the `variables` section of the JSON payload

[This transforms the query to the following:](https://www.dronedeploy.com/graphql?operationName=null&query=mutation%28%24input%3ACreateExportInput!%29{
%20%20createExport%28input%3A%24input%29{
%20%20%20%20export{
%20%20%20%20%20%20id
%20%20%20%20}
%20%20}
}
&variables={
%20%20"input"%3A{
%20%20%20%20"planId"%3A%20"MapPlan%3A5a0ddee5a6b7d90aecdc2f1d"%2C
%20%20%20%20"parameters"%3A%20{
%20%20%20%20%20%20%20%20"layer"%3A%20"ORTHOMOSAIC"
%20%20%20%20}
%20%20}
}
)

```text
mutation($input:CreateExportInput!){
  createExport(input:$input){
    export{
      id
    }
  }
}
```

With the variables:

```text
{
  "input":{
    "planId": "MapPlan:5a0ddee5a6b7d90aecdc2f1d",
    "parameters": {
        "layer": "ORTHOMOSAIC"
    }
  }
}
```

The raw request looks like:

```text
Authorization: Bearer <api_key>
POST /graphql
{
  "query": "mutation CreateExport($input:CreateExportInput!){createExport(input:$input){export{id}}}",
  "variables": {
    "input": {
      "planId": "MapPlan:5a0ddee5a6b7d90aecdc2f1d",
      "parameters": {
        "layer": "ORTHOMOSAIC"
      }
    }
  }
}
```

