# Triggers

Triggers allow your DroneDeploy App to respond to events happening on the DroneDeploy Platform. For example, you may want to kick off a pre-defined export once your map completes processing.

Triggers are associated with an App's Function. In order for a Trigger event to fire, the user who triggered the event needs to have the App installed, and the Function should have a Trigger defined. You can define Triggers using the `DroneDeploy CLI` and the `serverless.yml` file. For example:

```
service: IFTTT

provider:
  name: dronedeploy

app: # APP ID GOES HERE

plugins:
  - "@dronedeploy/dronedeploy-cli"

functions:
  ifttt-webhook:
    handlerPath: functions/webhook
    handler: dronedeploy
    memory: 128
    events:
      -trigger
        object-type: Export
        type: complete
    resources:
      tables:
        webhook-table:
          description: "stores endpoint for IFTTT webhook"
          columns:
            - name: endpoint
              type: Text
              encrypted: false
              length: 255
              description: "webhook endpoint for IFTTT"
```

## Listening to Triggers

Currently there is a reserved path under `/__ddtriggerfunction` on each DroneDeploy Function for listening to Trigger events.

Your code might look something like this:

```javascript
exports.routeHandler = function (req, res, ctx) {
  const path = req.path;
  switch(path) {
    case '/__ddtriggerfunction':
      triggerHandler(req, res, ctx);
      break;
  }
};
```

You can check out our [sample app](https://github.com/dronedeploy/app-examples/blob/master/IFTTT/functions/webhook/handler.js) to see how Triggers are handled.

## Supported Triggers

We currently support the following Triggers:

* Export:complete
* Folder:created
* MapPlan:complete
* MapPlan:workflow\_job\_complete
* ProgressPhotos:complete
* ProgressPhotosPlan:complete
* Project:created
* Plan:deleted
* StandAssessmentPlan:json\_uploaded

## Manually Executing Trigger Handler

**Note: These instructions are specific to a user with admin privileges**

1. Log into DroneDeploy and retrieve your scoped JWT token. See [here](ui-kit.md) for more info on retrieving a token.
2. In Postman (or other REST client) use this token to set the `Authorization` header for the API request
3. Using Postman, build a `POST` request to `https://www.dronedeploy.com/api/v2/trigger` which executes function triggers on-demand.
4. Executing the `POST` request should result in a 200 OK with `{}` as the response if successful
5. ```
   // Example Payload for StandAssessmentPlan:json_uploaded

   {
       "event_object_type": "StandAssessmentPlan",
       "event_type": "json_uploaded",
       "object_id": "<insert one plan_id here>",
       "user_id": "<org owner id>"
   }
   ```

## Troubleshooting

#### Attempting to execute a trigger function and receiving a 403 <a href="#users-attempting-to-execute-a-trigger-function-and-receiving-a-403" id="users-attempting-to-execute-a-trigger-function-and-receiving-a-403"></a>

If you are attempting to trigger a function and receiving a 403, it’s potentially because the payload is incorrect.

Make sure that:

1. You are an organization admin
2. The bearer token provided belongs to your user
3. The `user_id` is your user's ID
4. `object_id` is required in the “trigger” API payload and be an ID of the type of object for the trigger (i.e. Map Plan ID, Export ID, Folder ID, etc..)

Non-admin users must authenticate with their API key as a query param. The `user_id` is not necessary in the data object as it will be derived from the API key.

Example public request url:  `https://public-api.dronedeploy.com/v2/trigger?api_key=<api_key>`

