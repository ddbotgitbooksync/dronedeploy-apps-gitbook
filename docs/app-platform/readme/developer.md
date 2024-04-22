# Developer Mode

Developer mode is the way with which you can display DroneDeploy App Zones - areas within the UI where you can have apps.

You can enable Developer mode with the following steps:

1. Navigate into the App Market ![](../../../.gitbook/assets/developer\_mode\_1.png)
2. Navigate to the Developer tab ![](../../../.gitbook/assets/developer\_mode\_2.png)
3. Turn on Developer mode. Note that you may need to accept the developer agreements below the toggle. ![](../../../.gitbook/assets/developer\_mode\_3.png)
4. This will make various areas in DroneDeploy available for app development
   1.  Full list of app zones that can be specified in the `serverless.yml` configuration

       ```yaml
       map-page: # DataOverview (Explore page)
       auto-exports-explorer: # AutoExportsExplorer
       project-files-explorer: # Overlays (modal)
       preflight-checklist-page: # Checklist
       exports-page: # Exporter
       organization-app-management-page: # OrgAppManagement
       flight-planning-page: # PlanningOverview
       project-settings-page: # ProjectSettings
       user-settings-page: # Settings
       ```
