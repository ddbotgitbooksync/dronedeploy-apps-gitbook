# Projects

**What is a Project?**

A project is a collection of multiple flight plans and maps of the same site. A project may contain flight data collected during multiple flights from various points in time.

**Contents**

* [Projects.getCurrentlyViewed](projects.md#projects.getcurrentlyviewed)
* [Projects.team](projects.md#projects.team)

## Projects.getCurrentlyViewed

**Overview**

Returns the project that is the currently visible to the user. This method returns the project id and name.

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

[**Full Example**](../app-examples/example-projects.getcurrentlyviewed.md)

## Projects.team

**Overview**

Returns members who have access to current project. This method can be used only inside pages within the project. Otherwise, it throws an error.

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

[**Full Example**](../app-examples/projects.team.md)
