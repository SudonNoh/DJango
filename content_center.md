### 버튼 가운데 정렬

```html
<!DOCTYPE html>
<html lang="ko">

{% load static %}

<head>
    <meta charset="UTF-8">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-giJF6kkoqNQ00vy+HMDP7azOuL0xtbfIcaT9wjKHr8RbDVddVHyTfAAsrekwKmP1" crossorigin="anonymous">
    <title>TITLE</title>
    <link rel="icon" type="image/png" href="{% static 'images/icons/PNGNAME.png' %}">
    <style type="text/css">
        .layer {
            position: absolute;
            text-align: center;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            font-size: 50px;
        }
        .layer .content {
            display: inline-block;
            vertical-align: middle
        }
        .layer .blank {
            display: inline-block;
            width: 0;
            height: 100%;
            vertical-align: middle
        }
    </style>
</head>

<body>

    <div class="layer">

        <a class="btn btn-outline-secondary btn-lg" href="#" role="button">ENTER</a>
        <span class="blank"></span>

    </div>

</body>
</html>
```
