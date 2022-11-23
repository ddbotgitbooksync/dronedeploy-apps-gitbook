# Authentication

All API requests require an API key to be sent in the Authorization header.

{% hint style="info" %}
**If you already have access to our developer API, contact the** [**DroneDeploy Support Team**](mailto:support@dronedeploy.com) **for help retrieving your API key.**
{% endhint %}

{% hint style="info" %}
**If you would like access to our developer API, contact the** [**DroneDeploy Sales Team**](mailto:sales@dronedeploy.com) **for access to the API key for your enterprise or Developer Partner account.**
{% endhint %}

Once you have your API key it needs to be sent as an `Authorization` header:

```
POST /graphql?   Authorization: Bearer <api_key>
```

Your API key is associated with your own account and so the `viewer` query will return your user account details.

When using the API explorer you simply need to be logged in.
