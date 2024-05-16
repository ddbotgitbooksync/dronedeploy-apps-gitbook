# Map

What many developers think of as a map is known as a plan inside the API. Plans refer to information about the users flights or processed data. Please see [Plans](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/c927048f33aac44c8e61d230dc43194aca71784c/plans.md) for information about how to modify and access plan information.

The map api exposes method for developers to interact with the map on the user's screen.

* [Map.addTileLayer](map.md#map.addtilelayer)

**Note:** You must _.subscribe()_ to methods that draw onto the map. When unsubscribe is called the map changes will be removed.

```
var sub = dronedeployApi.Map.addTileLayer(urlTemplate, optionalOptions)
  .subscribe(() => {
    // This will remove your change from the map.
    sub.unsubscribe();
  });
```

Additionally, when you App is removed from the dom all pending subscriptions are destroyed which will in return remove any map change made.

## Map.addTileLayer

**Overview**

```javascript
var urlTemplate = String;
var optionalOptions = {
  errorTileUrl: String,
  maxZoom: Number,
  minZoom: Number,
};

dronedeployApi.Map.addTileLayer(urlTemplate, optionalOptions);
```

**Response**

```javascript
.subscribe(function(tileLayer){
  tileLayer.bringToBack();
  tileLayer.bringToFront();
  tileLayer.remove();
  tileLayer.setOpacity(0.4);
  tileLayer.setUrl(tileTemplate);
});
```

**Example**

```javascript
var urlTemplate = 'https://api.mapbox.com/styles/v1/mapbox/dark-v9/tiles/256/{z}/{x}/{y}';
var blankImage = 'data:image/gif;base64,R0lGODlhAQABAAAAACw=';
dronedeployApi.Map.addtileLayer(urlTemplate, {
  errorTileUrl: blankImage,
  maxZoom: 25,
  minZoom: 18,
});
```

[**Full Example**](https://github.com/dronedeploy/dronedeploy-apps-gitbook/blob/master/docs/map/map-api-example.md)
