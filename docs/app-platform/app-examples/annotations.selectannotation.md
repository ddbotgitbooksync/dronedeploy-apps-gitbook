# Annotations.selectAnnotation

```markup
<html>
  <head>
    <title></title>
    <script>
      var annotationId = 'a601d78ddc5fdef542728309894895b4a42dc333';
      var dd = new DroneDeploy({
        version: 1
      });

      dd.then(function(api){
        api.Annotations.selectAnnotation(annotationId).subscribe((annotation) => {
          console.log(annotation);
        });
      });

    </script>
  </head>
  <body>
    <h1>Annotation.selectAnnotation Example</h1>
  </body>
</html>
```
