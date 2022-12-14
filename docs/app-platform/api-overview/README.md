# Javascript API

## App Zones

{% embed url="https://www.youtube.com/watch?v=gsBPcHuA8r8&index=2&list=PLqOge_z8yN2EJ4ftDaY1XdbaneCRQTnvq" %}

## API Overview

{% embed url="https://www.youtube.com/watch?v=ilrWHM95DY0&index=3&list=PLqOge_z8yN2EJ4ftDaY1XdbaneCRQTnvq" %}

All communication to DroneDeploy is available by instantiating the global api object

```javascript
new DroneDeploy({version: 1}).then(function(dronedeployApi){
  console.log(dronedeployApi);
})
```

_**Note**_: The following code represents example usage. Replace `Class` and `method` with the actual class and method from the API.

You can listen to the result of any `dronedeployApi` call via promises.

```javascript
new DroneDeploy({version: 1}).then(function(dronedeployApi){
  dronedeployApi.Class.method(exampleParameter)
    .then(function(response){
      console.log(response);
    }, function(error){
      console.log(error);
    });
});
```

You can listen to the result of any call via promises.

```javascript
dronedeployApi.Class.method(exampleParameter).then(function(response){
  console.log(response);
}, function(error){
  console.log(error);
});
```

_Note: The promise polyfill is loaded into every app._ [_Read More about Promises_](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Promise)

If you are subscribing to a stream of data and want to receive multiple values you should use `.subscribe`.

```javascript
new DroneDeploy({version: 1}).then(function(dronedeployApi){
  dronedeployApi.Class.method(exampleParameter).subscribe(
    function(result){ console.log(result)},
    function(error){ console.log(error)},
    function(){ console.log('complete')}
  ); 
});
```

_Note: This pattern is inspired by rxjs, but rxjs is not loaded into apps._
