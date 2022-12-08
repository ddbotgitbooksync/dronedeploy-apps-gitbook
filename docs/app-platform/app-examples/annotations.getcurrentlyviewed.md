# Annotations.getCurrentlyViewed

```markup
<html>
  <head>
    <title></title>
    <script>
      let planGeometry = {};

      var dd = new DroneDeploy({
        version: 1
      });

      dd.then(function(api){
        api.Annotations.getCurrentlyViewed().subscribe((plan) => {
          console.log(plan);
        });
      });

    </script>
  </head>
  <body>
    <h1>Annotation.getCurrentlyViewed Example</h1>
  </body>
</html>
```
