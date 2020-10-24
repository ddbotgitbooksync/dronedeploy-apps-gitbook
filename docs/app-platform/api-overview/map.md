# Map

What many developers think of as a map is known as a plan inside the API. Plans refer to information about the users flights or processed data. Please see [Plans](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/c927048f33aac44c8e61d230dc43194aca71784c/plans.md) for information about how to modify and access plan information.

The map api exposes methods for developers to interact with the map on the user's screen.

* [Map.addImageOverlay](map.md#mapaddimageoverlay)
* [Map.panTo](map.md#mappanto)
* [Map.addTileLayer](map.md#mapaddtilelayer)
* [Map.addPolygon](map.md#mapaddpolygon)

**Note:** You must _.subscribe\(\)_ to methods that draw onto the map. When unsubscribe is called the map changes will be removed.

```text
var sub = dronedeployApi.Map.addPolygon(latLng)
  .subscribe(() => {
    // This will remove your change from the map.
    sub.unsubscribe();
  });
```

Additionally, when you App is removed from the dom all pending subscriptions are destroyed which will in return remove any map change made.

## Map.addImageOverlay

**Overview**

```javascript
var imageUrl = String;
var bounds = [{ lat: Number, lng: Number }, ....];
dronedeployApi.Map.addImageOverlay(imageUrl, bounds)
  .subscribe(function(overlay){ console.log(overlay) });
```

**Response**

```javascript
.subscribe(function(overlay){
  overlay.bringToBack();
  overlay.bringToFront();
  overlay.remove();
  overlay.setOpacity(0.4);
  overlay.setUrl(imageUrl);
});
```

[**Full Example**](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/c927048f33aac44c8e61d230dc43194aca71784c/map/map-api-example.md)

## Map.panTo

```javascript
var location = LatLng;
var optionalOptions = {zoom: 20};
dronedeployApi.Map.panTo(location, optionalOptions);
```

[**Full Example**](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/c927048f33aac44c8e61d230dc43194aca71784c/map/map-api-example.md)

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

[**Full Example**](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/c927048f33aac44c8e61d230dc43194aca71784c/map/map-api-example.md)

## Map.addPolygon

**Overview**

```javascript
var latLngs = [{lat: Number, lng: Number}, ...];
var optionalOptions = {
  color: String,
  fill: Boolean,
  fillColor: String,
  opacity: Number,
  weight: Number,
};
dronedeployApi.Map.addPolygon(latLngs, optionalOptions)
  .subscribe(function(annotation){ console.log(annotation) });
```

**Response**

```javascript
.subscribe(function(polygon){
  polygon.bringToBack();
  polygon.bringToFront();
  polygon.getCenter().then(function(latLng){ console.log(latLng) });
  polygon.getLatLngs().then(function(latLngs){ console.log(latLngs) });
  polygon.remove();
  polygon.setLatLngs([{lat: 3, lng: 3}, ...]);
  polygon.setOpacity(0.4);
});
```

[**Full Example**](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/c927048f33aac44c8e61d230dc43194aca71784c/map/map-api-example.md)

