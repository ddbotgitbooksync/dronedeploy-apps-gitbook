# CadOverlay.prepare

![](https://github.com/ddbotgitbooksync/dronedeploy-apps-gitbook/tree/9b55f7579d9109d7de2536e0970da9247a61d33c/docs/cadoverlay/assets/cadoverlay-prepare.png)

```markup
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>

<body>
    <h3 class="title sans">CadOverlay.preapre example</h3>
    <span id="cadoverlay"></span>
    <script>
        const cadOverlayOutput = document.getElementById('cadoverlay');

        new DroneDeploy({
                version: 1
            })
            .then(function(dronedeployApi) {
                return dronedeployApi.CadOverlay.prepare()
            })
            .then(function(id) {
                cadOverlayOutput.innerHTML = `ID: ${id}`;
            });
    </script>
</body>

</html>
```

