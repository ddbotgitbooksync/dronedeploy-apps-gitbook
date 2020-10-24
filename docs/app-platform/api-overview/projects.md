# Projects

**What is a Project?**

A project is a collection of multiple flight plans and maps of the same site. A project may contain flight data collected during multiple flights from various points in time.

**Contents**

* [Projects.getCurrentlyViewed](projects.md#projectsgetcurrentlyviewed)
* [Projects.team](projects.md#projectsteam)

## Projects.getCurrentlyViewed

**Overview**

Returns the project that is the currently visible to the user. This method returns project id and name.

**Example Call**

```javascript
// Get the current one time
dronedeployApi.Projects.getCurrentlyViewed()
  .then(function(project){
    console.log(project);
  });

// Will be called each time the project changes
dronedeployApi.Projects.getCurrentlyViewed()
  .subscribe(function(project){
    console.log(project);
  });
```

**Example Response**

```javascript
{
  "id": "12ab34cd56ef78gh90ij12kl"
}
```

[**Full Example**](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/50f844b3b7983112188c898458a5c1fad335e997/projects/example-projects.getcurrentlyviewed.md)

## Projects.team

**Overview**

Returns members who have access to current project. This method can be used only inside project's pages, otherwise it throws error.

**Example Call**

```javascript
// Get members for current project one time
dronedeployApi.Projects.team()
  .then(function(members){
    console.log(members);
  });

// Will be called each time the project changes
dronedeployApi.Projects.team()
  .subscribe(function(members){
    console.log(members);
  });
```

**Example Response**

```javascript
[
  {
    "permission": "editor",
    "username": "test_user@example.com"
  },
  {
    "permission": "editor",
    "username": "test_user_2@example.com"
  }
]
```

[**Full Example**](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/50f844b3b7983112188c898458a5c1fad335e997/projects/example-projects.team.md)

