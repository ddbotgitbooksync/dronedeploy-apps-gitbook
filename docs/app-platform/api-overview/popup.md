# Popup

**Overview**

Open a closable popup window over the map and add additional content onto the popup itself.

**Example Call**

```javascript
// Open the popup
var title = 'Popup Title';
dronedeployApi.Popup.open(title);

// Close the popup
dronedeployApi.Popup.close();
```

**How to Use**

There are several steps you want to keep in mind when utilizing the popup. You will need two separate plugins, one for the main launch point and one for the popup itself.

1. Drag your main plugin (that opens the popup) into any App Zone on the sidebar.
2. Once you open the popup using your main plugin, you can add another plugin to the App Zone on the popup window itself.
3. Make sure to specify that your popup plugin belongs to the same app as your main plugin when prompted!

[**Full Example**](../app-examples/example-popup.basic.md)

****
