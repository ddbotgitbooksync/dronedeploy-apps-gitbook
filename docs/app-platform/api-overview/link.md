# Link

## Link.open

**Overview**

Since apps run on Web, iOS, and Android, some things like links can be a little more complicated. In order to abstract this complexity, we've added a method `dronedeployApi.Link.open` to make this easier on native devices.

**Example**

```javascript
// Will open in new window, similar to `window.open('https://www.google.com/')`
dronedeployApi.Link.open('https://www.google.com/');
```

[**Example: Link.open**](../app-examples/example-link.open.md)
