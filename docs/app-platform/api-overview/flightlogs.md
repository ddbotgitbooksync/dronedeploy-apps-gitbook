# FlightLogs

## FlightLogs.getLogsFromPlan

**Overview**

```javascript
const planId = String;
dronedeployApi.FlightLogs.getLogsFromPlan(planId);
```

* [Sample Flight Log](../app-examples/sample-flight-log.md)

**Example**

```javascript
dronedeployApi.FlightLogs.getLogsFromPlan('57eaa66d2a2b43fa1249c76c')
  .then(function(logs){ console.log(logs) });
```

**Example Response**

```javascript
[
  downloadUrl: "https://s3.amazonaws.com/drone-deploy-flight-logs/57eaa66d2a2b43fa1249c76c/57eaa66d2a2b43fa1249c76c-09-29-105201-197_2016-09-29-110228-607.log"
  duration: "10 minutes"
  startTime:"29 Sep 2016 - 10:52"
]
```

[**Full Example**](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/c927048f33aac44c8e61d230dc43194aca71784c/flightlogs/example-flightlog.getlogsfromplan.md)

