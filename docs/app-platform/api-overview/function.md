# Function

##

DroneDeploy Functions is your tool for writing, running, and deploying backend code functionality.

DroneDeploy Functions uses serverless architecture running on the DroneDeploy Platform. You can write Node.js code to build out custom backend functionality and hook into things like Datastore and Triggers seamlessly.&#x20;

Note: This only matters if you’re using a [Function](https://developer-docs.dronedeploy.com/app-platform/introduction/functions).&#x20;

* ​[Functions.getUrl](function.md#map.addimageoverlay)​​

### Functions.getUrl <a href="#map.addimageoverlay" id="map.addimageoverlay"></a>

**Overview**

Get the URL of the Function. Once you have your function url, you can use it to call the Function from your App's UI. You do this by passing the name of the function into the `getUrl` API method.&#x20;

```
const dronedeploy = new DroneDeploy({version: 1});
const api = await dronedeploy;

const FUNCTION_NAME = "ifttt-webhook";

// Grabs the URL of the function to call by name of function
const functionUrl = await api.Functions.getUrl(FUNCTION_NAME);

fetch(functionUrl);
```

​[**Full Example**](https://github.com/dronedeploy/app-examples/blob/master/IFTTT/app/js/script.js)
