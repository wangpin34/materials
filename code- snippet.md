# CSS

# HTML

```html
<!DOCTYPE html>
<html>
<head>
<meta name="application-name" content="snow white">
<meta name="generator" content="wang pin">
<meta name="description" content="Free Web tutorials">
<meta name="keywords" content="HTML,CSS,XML,JavaScript">
<meta name="author" content="wang pin">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<!--HTML4 charset def-->
<meta http-equiv="content-type" content="text/html; charset=UTF-8">
<!--HTML5 charset def-->
<meta charset="UTF-8">
<link rel="icon" href="/assets/icon.ico" type="image/x-icon">
<title></title>
<link rel="stylesheet" type="text/css" href="style.css" >
<style>
 body {
  margin: 0; /* Remove default margin */
 }
</style>
</head>
<body>

</body>
<script type="text/javascript" src="/js/a.js"></script>
<script type="text/javascript" src="/js/a.js" async></script>
<script type="text/javascript" src="/js/a.js" defer></script>
<script type="text/javacript">
 document.addEventListener('DOMContentLoaded', function(){})
 window.onload = function(){}
 window.on('load', function(){})
 window.addEventListener('load', function(){})
 document.onscroll = function(){}
</script>
</html>
```

# Javascript
* 兼容性的 event
```
function handleClick(event){
  event = event||window.event;
  //do something
}

<button onclick="handleClick(event)">pass event</button>
<button onclick="handleClick()">don't pass event</button>
```
有的浏览器必须显示传递 event 对象给处理函数，比如 firefox，有的浏览器不需要，因为 event 对象已经存储到 window 下，比如低版本的 ie。chrome 和较新版本的 ie 同时支持这两种风格。

* listener
```javascript
function addListener(element, eType, listener, useCapture){
  if(!element) throw new Error('No element provided');
  
  if(element.addEventListener){
    element.addEventListener(eType, function(event){
     listener&&listener(event||window.event);
    }, useCapture)
  }else{
    element.attach('on' + eType, function(event){
     listener&&listener(event||window.event)
    })
  }
}
```

* 数组元素去重
```javascript
function uniq2Array(arr) { 
    return arr.filter(function(v, index) { return arr.indexOf(v)=== index})
}
```
* 日期
  * 字符串转日期
  * 日期转字符串
  * n天前 or n天后

* 

# Nodejs

# Android
* 显示外部（不是res文件中的）图片
```java
 Bitmap myBitmap = BitmapFactory.decodeFile(path);
 imageView.setImageBitmap(myBitmap);
```
