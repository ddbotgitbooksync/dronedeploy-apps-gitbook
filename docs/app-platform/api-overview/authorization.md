# Authorization

* [getScopedToken](authorization.md#undefined)

## getScopedToken

`Authorization.getScopedToken` returns an authenticated JWT token to make further calls to the DroneDeploy API. This token will be set as part of the `Authorization` header as a `Bearer` token inside of subsequent requests.

### Example Usage

```
const dronedeploy = new DroneDeploy({version: 1});

async function callApiUrl(url) {
  const api = await dronedeploy;

  // Get a token to ensure auth when calling our api
  const token = await api.Authorization.getScopedToken();
  
  const options = {
    method: "POST",
    body: JSON.stringify({data: "hello world"}),
    headers: {
        Authorization: `Bearer ${token}`
    }
  }
  return fetch(url, options);
}

```
