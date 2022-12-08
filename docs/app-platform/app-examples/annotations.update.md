# Annotations.update

```markup
<html>
  <head>
    <title></title>
    <script>
      var dd = new DroneDeploy({
        version: 1
      });

      dd.then(function(api) {
        const propertiesToUpdate = {
          color: '#888888'
          description: 'My new annotation description',
          geometry: [
            { lat: 35, lng: 36 },
            { lat: 33, lng: 34 },
            { lat: 30, lng: 31 },
          ],
        };

        api.Annotations.getCurrentlyViewed().then(function(annotation) {
          api.Annotations.update(
            annotation.id,
            propertiesToUpdate
          );
        });
      });
    </script>
  </head>
  <body>
    <h1>Annotation.update Example</h1>
  </body>
</html>
```
