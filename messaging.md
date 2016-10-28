# Messaging (Arrival 11/1/2016)
## Messaging.showToast
**Overview**

```javascript
const message = String;
const optionalOptions = {timeout: Number};
window.dronedeploy.Messaging.showToast(message, optionalOptions)
  .subscribe((toastObj) => console.log(toastObj));
```

**Examples**
```javascript
window.dronedeploy.Messaging.showToast('Example Message');
```

```javascript
// timeout after 5 seconds
window.dronedeploy.Messaging.showToast('Example Message', {timeout: 5000});
```

```javascript
const neverTimeout = -1;
window.dronedeploy.Messaging.showToast('Example Message', {timeout: neverTimeout})
  .subscribe((toastObj) => {
    // Programmatically remove a toast
    setTimeout(() => toastObj.remove(), 1000)
  });
```

**Response**

```javascript
{
  // Remove the toast from the screen
  remove: Function
}
```