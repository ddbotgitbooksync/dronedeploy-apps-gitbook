# Annotations

**Overview**

<figure><img src="../../.gitbook/assets/Screen Shot 2022-12-07 at 2.38.47 PM.png" alt=""><figcaption></figcaption></figure>

* [Annotations.get](annotations.md#annotations.get)

## Annotations.get

**Overview**

This function returns all the annotations for a given plan.

```javascript
const planId = String;
const optionalOptions = {
  comments: boolean, // embed comments into annotations response
};
dronedeployApi.Annotations.get(planId, optionalOptions)
  .then(function(annotations){ console.log(annotations) })
```

**Example Call**

```javascript
dronedeployApi.Annotations.get('5730dc11929d2465038183ab', {comments: true})
  .then(function(annotations){ console.log(annotations) })
```

[**Full Example**](../app-examples/example-annotations.get.md)

**Example Response**

```javascript
[
  {
    "info": {
      "geometry": [
        {
          "type": "Coords",
          "value": {
            "lat": 35.92649941843441,
            "lng": -96.7485022544861
          },
          "isPending": false
        }
      ]
    },
    "userId": "56282ec3098f6b3987e2e937",
    "fillColor": "#40ccde",
    "dateModified": 1477425822658,
    "color": "#00bbd3",
    "comments": [],
    "options": 0,
    "geometry": {
      "lat": 35.92649941843441,
      "lng": -96.7485022544861
    },
    "annotationType": "LOCATION",
    "id": "580fba9ecb5fda701d819131",
    "planId": "5730dc11929d2465038183ab",
    "type": "marker",
    "dateCreation": 1477425822658,
    "description": ""
  },
  {
    "info": {
      "geometry": [
        {
          "type": "Area",
          "value": 3935.274554447226,
          "isPending": false
        }
      ]
    },
    "userId": "56282ec3098f6b3987e2e937",
    "fillColor": "#40ccde",
    "dateModified": 1477425814283,
    "color": "#00bbd3",
    "comments": [],
    "options": 0,
    "geometry": [
      {
        "lat": 35.92754630265763,
        "lng": -96.74921572208406
      },
      {
        "lat": 35.927016346401395,
        "lng": -96.74940884113313
      },
      {
        "lat": 35.92681218197787,
        "lng": -96.74877047538757
      },
      {
        "lat": 35.92742467366698,
        "lng": -96.74858808517457
      }
    ],
    "annotationType": "VOLUME",
    "id": "580fba96cb5fda701d819130",
    "planId": "5730dc11929d2465038183ab",
    "type": "polygon",
    "dateCreation": 1477425814283,
    "description": ""
  },
]
```
