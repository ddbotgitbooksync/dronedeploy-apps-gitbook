# Track

**Overview**

* [Track.successCondition](track.md#tracksuccesscondition)

{% hint style="info" %}
Note: `Track.send` and accessing tracking data are deprecated as of September 2022
{% endhint %}

## Track.successCondition

**Overview**

`Track.successCondition()` should be called when the user performs the desired action in your app. This could be making a purchase, running a query, downloading a report, etc. This is necessary before [submitting your app for approval](../platform-policy/success-condition.md).

**Example Call**

```javascript
dronedeployApi.Track.successCondition()
```
