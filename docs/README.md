# Introduction

Since 2015, tens of thousands of DroneDeploy users have mapped more than 310 million acres in various different industries. Our API allows outside developers to build apps directly into the DroneDeploy user interface.

Once a user installs an app it will run on DroneDeploy.com, Android and iOS DroneDeploy apps. All apps are written in HTML, CSS, and JavaScript. Apps have the capability to access and modify DroneDeploy features. Additionally, any JavaScript framework or library can be used to develop an app.

### How to Quickly Get Started

1. Ensure you have a [DroneDeploy API key](app-platform/introduction/getting-started.md#prerequisites) to begin development
2. You will need to have [npm](https://www.npmjs.com/) and [node.js](https://nodejs.org/en/) installed.
3.  We use the [serverless](https://serverless.com/) platform for deployment. You will need to install this globally

    ```
     $ npm install -g serverless
    ```
4. Download a [simple example](https://s3.amazonaws.com/drone-deploy-plugins/templates/dronedeploy-app-hello-world.zip) or [full example](https://s3.amazonaws.com/drone-deploy-plugins/templates/dronedeploy-expand-example.zip) of an app template and unzip the folder.
   1.  Add a `package.json` file to folder like this:

       ```json
       {
         "name": "my-new-app",
         "version": "0.0.0",
         "license": "UNLICENSED",
         "engines": {
           "node": ">=16.14.x",
         },
         "devDependencies": {
           "@dronedeploy/dronedeploy-cli": "2.1.2",
           "serverless": "3.27.0"
         }
       }
       ```
   2.  Add a `serverless.yml` file to the same folder like this (for a full list of available app zones see [here](app-platform/readme/developer.md)):

       ```yaml
       service: my-new-app
       app: # FILLME AppId
       provider:
         name: dronedeploy
       plugins:
         - '@dronedeploy/dronedeploy-cli'

       resources:
         app-zones:
           map-page: # DataOverview (Explore page)
             directoryPath: /app
       ```
   3. From the command line inside the folder run `npm install` to install dependencies
   4.  Configure the command line to log into DroneDeploy using your API key

       ```
       serverless config dronedeploy-credentials --provider=dronedeploy --key=<YOUR API KEY>
       ```
5. Agree to the Developer Agreement and turn on "[Developer Mode](app-platform/readme/developer.md)".
6. To deploy your app for testing from the command line inside your app's directory:
   1. Create your app (this will populate the `app` field in `serverless.yml`)
      1. `sls deploy app --name "my app name"`
   2. Deploy/update your app's files (this will upload your files to DroneDeploy and make your app's code visible in the app zones specified in `serverless.yml`)
      1. `sls deploy app version`
7. Review our documentation to use our "Getting Started UI Kit" components and other tools for quick UI development.
8. Lastly, start developing on top of the starter template.&#x20;

_Hint: Open the javascript console to view the dronedeployApi._
