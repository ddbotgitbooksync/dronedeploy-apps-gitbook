# Plans

**What is a Plan?**

A plan contains the flight data, drone data, image information, and the map assets. The same plan is used across planning, flight, uploading, and post-processed viewing.

**Contents**

* [Plans.getCurrentlyViewed](plans.md#plans.getcurrentlyviewed)
* [Plans.all](plans.md#plans.all)
* [Plans.update](plans.md#plans.update)
* [Plans.create](plans.md#planscreate)
* [Plans.hideGeometry](plans.md#planscreate-1)
* [Plans.showGeometry](plans.md#planscreate-2)

## Plans.getCurrentlyViewed

&#x20;**Overview**&#x20;

Returns the plan that is currently visible to the user. For example, if the user is on the Explore or Fly page, the returned plan will be the plan they are viewing.

&#x20;**Example Call**&#x20;

```javascript
// Get the current one time
dronedeployApi.Plans.getCurrentlyViewed()
  .then(function(plan){
    console.log(plan);
  });

// Will be called each time the plan changes
dronedeployApi.Plans.getCurrentlyViewed()
  .subscribe(function(plan){
    console.log(plan);
  });
```

&#x20;**Example Response**&#x20;

```javascript
{
  "accuracy": {
    "xRMSE": 35.527931,
    "yRMSE": 4.964015,
    "zRMSE": 1.343646,
    "gcpAccuracyDownload": "String of the ZIP file",
  },
  "id": "57e0761f21303e5214b6ae31",
  "camera": {
    "v_proj": 0.9,
    "h_proj": 0.9,
    "name": "DJIX3",
    "capture_delay": 0,
    "yres": 2250,
    "xres": 4000,
    "sensor_height": 4.55,
    "sensor_width": 6.17,
    "id": 18,
    "focal": 3.6,
    "min_capture_period": 2
  },
  "deleted": false,
  "sketchfabModel": "https://sketchfab.com/models/cc462c22851847c78768d0318221a963",
  "status": "complete",
  "geometry": [
    {
      "lat": 35.92712713888889,
      "lng": -96.7493288888889
    },
    {
      "lat": 35.92712713888889,
      "lng": -96.74831555555555
    },
    {
      "lat": 35.92519230555555,
      "lng": -96.74831555555555
    },
    {
      "lat": 35.92519230555555,
      "lng": -96.7493288888889
    }
  ],
  "info": {
    "altitude": 75
  },
  "location": {
    "lat": 35.92583194444444,
    "lng": -96.74852777777778
  },
  "name": "Untitled Map",
  "username": "daniel@dronedeploy.com",
  "frontlap": 70,
  "sidelap": 60,
}
```

&#x20;**plan.status**&#x20;

* "new":  Before the plan has been flown
* "queued":  Plan is waiting to be processed
* "processing":  Plan is being processed
* "failed":  Plan failed during processing
* "complete":  Plan has finished processing

[**Full Example**](https://github.com/dronedeploy/dronedeploy-apps-gitbook/blob/master/docs/plans/example-plans.getcurrentlyviewed.md)

[**Full Example - Get Area of Plan**](https://github.com/dronedeploy/dronedeploy-apps-gitbook/blob/master/docs/plans/example-plans-get-area.md)

## Plans.all

&#x20;**Overview**&#x20;

Get an array of all the users plans in memory. We store the 50 most recent and any plan a user loads in memory. Optionally, there is the ability to get the plans paginated.&#x20;

&#x20;**Example Call**&#x20;

```javascript
// Get all the users plan one time
dronedeployApi.Plans.all()
  .then(function(plans){
    console.log(plans);
  });

// Will be called each time a plan changes
dronedeployApi.Plans.all()
  .subscribe(function(plans){
    console.log(plans);
  });
  
// Paginated
var paginated: boolean;
var page: number;
var status: string;

dronedeployApi.Plans.all(paginated, page, status)
  .then(function(plans){
    console.log(plans);
  });
```

&#x20;**Example Response**&#x20;

```javascript
[
  {
    "id": "17e0761f21303e5214b6ae31",
    "camera": {...},
    "deleted": false,
    "geometry": [...],
    "info": {...},
    "location": {...},
    "name": "Plan 1",
    "username": "daniel@dronedeploy.com",
    "sketchfabModel": "https://sketchfab.com/models/cc462c22851847c78768d0318221a963",
  },
  {
    "id": "87e0761f21303e5214b6ae31",
    "camera": {...},
    "deleted": false,
    "geometry": [...],
    "info": {...},
    "location": {...},
    "name": "Plan 2",
    "username": "daniel@dronedeploy.com",
    "sketchfabModel": "https://sketchfab.com/models/dd462c22851847c78768d0318221a963",
  }
]
```

[**Full Example**](https://github.com/dronedeploy/dronedeploy-apps-gitbook/blob/master/docs/plans/example-plans.all.md)

## Plans.update

&#x20;**Overview**&#x20;

Plans.update allows you to update specific fields within the flight plan model.

Please reference the fieldsToUpdate variable in the following code for the fields updatable by this api method.

```javascript
const planIdToUpdate = String;
const fieldsToUpdate = {
  // These are the fields that can be updated on the plan
  name: String,
  altitude: Number, // in meters
  geometry: [{lat: Number, lng: Number}, ....],
  frontlap: Number,
  sidelap: Number,
  geometry: {lat: number, lng: number},
  frontlap: Number, // allowed range: 15 - 95%
  sidelap: Number, // allowed range: 15 - 95%
  camera: {
    id: Number,
    capture_delay: Number,
    focal: Number,
    h_proj: Number,
    min_capture_period: Number,
    name: String,
    sensor_height: Number,
    sensor_width: Number,
    v_proj: Number,
    xres: Number,
    yres: Number,
  },
  waypoints: [
    {
      alt: Number // the altitude of the waypoint - in meters
      lat: Number // the latitude of the waypoint - floating point
      lng: Number //the longitude of the waypoint - floating point
    }
  ]
};
dronedeployApi.Plans.update(planIdToUpdate, fieldsToUpdate);
```

**Note:** Save the plan's geometry on the planning page to automatically re-calculate the drone's flight path.

**Note:** Save the plan's waypoints on the planning page to change the drones flight path manually. If you decide your app needs to alter waypoints, this is considered a privileged action and the user will be asked if they wish to allow it on a per plan basis.

**Warning:** Waypoint changes may be overwritten my manual updates by the user to their flight geometry via the interactive map. Any waypoint changes should be in direct response to a [Plans.getCurrentlyViewed](https://www.gitbook.com/book/dronedeploy/dronedeploy-apps/edit), and either ignore, or handle changes to geometry, based on what your app is trying to achieve. [Please see this example for an example.](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/c927048f33aac44c8e61d230dc43194aca71784c/plans/example-plans.update-waypoints.md)

**Warning:** Changing geometry will overwrite any changes to waypoints, by recalculating the optimal flight path as per DD's calculation code. [Please see this example for an example.](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/c927048f33aac44c8e61d230dc43194aca71784c/plans/example-plans.update-waypoints.md)

&#x20;**Example Call**&#x20;

```javascript
dronedeployApi.Plans.update('57e0761f21303e5214b6ae31', {
  name: 'New Name',
  geometry: [
    {lat: 56.567259707222206,lng: -78.90349675},
    {lat: 37.717259707222226,lng: -78.88330925000001},
    {lat: 37.70100590388889,lng: -78.88330925000001},
    {lat: 37.70100590388889,lng: -78.90349675}
  ],
  frontlap: 70, // allowed range: 15 - 95%
  sidelap: 45, // allowed range: 15 - 95
  waypoints: [
    {lat: 56.567259707222206,lng: -78.90349675, alt: 100},
    {lat: 37.717259707222226,lng: -78.88330925000001, alt: 50},
    {lat: 37.70100590388889,lng: -78.88330925000001, alt: 50},
    {lat: 37.70100590388889,lng: -78.90349675, alt: 50}
  ],
  camera: {
    id: 11245,
    capture_delay: 0,
    focal: 4.7,
    h_proj: 0.9,
    min_capture_period: 2,
    name: 'MP4K',
    sensor_height: 4.55,
    sensor_width: 6.17,
    v_proj: 0.9,
    xres: 4000,
    yres: 3000,
  },
});
```

[**Full Example**](https://github.com/dronedeploy/dronedeploy-apps-gitbook/blob/master/docs/plans/example-plans.update.md)

[**Full Example - Change Waypoints**](https://github.com/dronedeploy/dronedeploy-apps-gitbook/blob/master/docs/plans/example-plans.update-waypoints.md)

## Plans.create <a href="#planscreate" id="planscreate"></a>

&#x20;**Overview**&#x20;

Plans.create allows you to create a new plan with an array of coordinates and an options object.

&#x20;**Example Call**&#x20;

```javascript
var geometry = [
  {lat: 35.92778956007768, lng: -96.74685001373292},
  {lat: 35.92524492896255, lng: -96.74667120678352},
  {lat: 35.92532220011748, lng: -96.74959659576417},
  {lat: 35.92778151526379, lng: -96.7496186761855},
];
var options = { name: 'Example Plan', geometry: geometry };

// Returns the id of the newly created plan
dronedeploy.Plans.create(options)
  .then(function(planId) {
    console.log(planId);
  });
```

[**Full Example**](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/c927048f33aac44c8e61d230dc43194aca71784c/plans/example-plans.create.md)

## Plans.hideGeometry <a href="#planscreate" id="planscreate"></a>

&#x20;**Overview**&#x20;

Plans.hideGeometry hides the plans geometry.

&#x20;**Example Call**&#x20;

```javascript
var planId = '1234';

// Returns the id of the plan.
dronedeploy.Plans.hideGeometry(planId);
```

## Plans.showGeometry <a href="#planscreate" id="planscreate"></a>

&#x20;**Overview**&#x20;

Plans.showGeometry shows the plans geometry.

&#x20;**Example Call**&#x20;

```javascript
var planId = '1234';

// Returns the id of the plan.
dronedeploy.Plans.showGeometry(planId);
```

