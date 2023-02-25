## 多媒體

#### media.html

```html
<!doctype html>
<html>

<head>
  <meta charset="UTF-8">
  <title>Video Test</title>
</head>

<body>

  <video src="windtunnel.mp4" width="320" height="262" controls>
    您的瀏覽器不支持 HTML5 視頻。 對不起。
  </video>


  <video id="video" controls width="320" height="262">
    <source src="windtunnel.webm" type="video/webm">
    <source src="windtunnel.mp4" type="video/mp4">
    <source src="windtunnel.ogg" type="video/ogg">
    您的瀏覽器不支持 HTML5 視頻。 對不起。
  </video>


</body>

</html>
```