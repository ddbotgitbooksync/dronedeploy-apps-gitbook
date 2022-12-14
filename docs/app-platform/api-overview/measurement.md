# Measurement

This is a wrapper for our REST measurement API, [https://help.dronedeploy.com/hc/en-us/articles/1500004860581-Measurements-API](https://help.dronedeploy.com/hc/en-us/articles/1500004860581-Measurements-API), allowing you to make these calls inside DroneDeploy apps.

* [Elevation of Point](measurement.md#elevation-of-point)
* [Elevation of Points](measurement.md#elevation-of-points)
* [Elevation of Line](measurement.md#elevation-of-line)
* [Volume of Points](measurement.md#volume-of-points)

## Elevation of Point

&#x20;**Example Call**

```javascript
dronedeployApi.Measurement.getElevationOfPoint(plan.id, {lat: 35.9272, lng: -96.7493})
  .then(function(jsonResult){
    console.log(jsonResult);
  });
```

**Example Response**

```javascript
{
  "lat": 35.9272,
  "lng": -96.7493,
  "aspect": 100.57501983642578,
  "elevation": -2.0494751930236816,
  "slope": 7.686941623687744
}
```

[**Full Example**](../app-examples/measurement\_example.md)

## Elevation of Points

**Example Call**

```javascript
dronedeployApi.Measurement.getElevationOfPoints(plan.id, [{lat: 35.9272, lng: -96.7493}, {lat: 35.9272, lng: -96.7493}])
  .then(function(jsonResult){
    console.log(jsonResult);
  });
```

**Example Response**

```javascript
[
  {
    "lat": 35.9272,
    "lng": -96.7493,
    "aspect": 100.57501983642578,
    "elevation": -2.0494751930236816,
    "slope": 7.686941623687744
  },
  {
    "lat": 35.9282,
    "lng": -96.7493,
    "aspect": 100.57501983642578,
    "elevation": -2.0494751930236816,
    "slope": 7.686941623687744
  },
]
```

[**Full Example**](../app-examples/measurement\_example.md)

## Elevation of Line

**Example Call**

```javascript
dronedeployApi.Measurement.getElevationOfLine(plan.id, [{lat: 35.9272, lng: -96.7493}])
  .then(function(jsonResult){
    console.log(jsonResult);
  });
```

**Example Response**

```javascript
{
  "length": 107.35063384719186,
  "endpoints": [
    [
      35.926247,
      -96.748958
    ],
    [
      35.926738,
      -96.747933
    ]
  ],
  "dx": 0.5394504213426726,
  "points": 200,
  "profile": [
    -3.2126803398132324,
    -2.9078261852264404,
    -2.5082149505615234,
    ....
  ]  
}
```

[**Full Example**](../app-examples/measurement\_example.md)

## Volume of Points

**Example Call**

```javascript
var geometry = [{lat: 35.9272, lng: -96.7493}, {lat: 35.9272, lng: -96.7493}, {lat: 35.9272, lng: -96.7493}];
var optionalVolumeSetting = 'lowest'; // will default to fit -- See https://help.dronedeploy.com/hc/en-us/articles/1500004963922-Volume-Measurement-with-Drones (section: Selecting the Right Base Plane)
dronedeployApi.Measurement.getVolume(plan.id, geometry, optionalVolumeSetting)
  .then(function(jsonResult){
    console.log(jsonResult);
  });
```

**Example Response**

```javascript
[
  {  
    "baseplane_type": "fit", 
    "cut": 26153.559188015362, 
    "fill": -18900.181208767106, 
    "polygon": "POLYGON(6.535406112670899 46.655990545464206,6.5360498428344735 46.655710711675226,6.535298824310304 46.654561905156164,6.534655094146729 46.654723917810095,6.535406112670899 46.655990545464206)",
    "volume": 7253.377979248256 
  }
]
```

[**Full Example**](../app-examples/measurement\_example.md)
