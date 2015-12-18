# css

# html
* 外部css
```
<link rel="stylesheet" type="text/css" href="style.css" >
```
* content type
```
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
```
* icon
```
<link rel="icon" href="D:/workspace/I.jpg" type="image/x-icon">
```

# js
* 兼容性的 event
```
function handleClick(event){
  event = event||window.event;
  //do something
}

<button onclick="handleClick(event)"></button>
<button onclick="handleClick()"></button>
```
有的浏览器必须显示传递 event 对象给处理函数，比如 firefox，有的浏览器不需要，因为 event 对象已经存储到 window 下，比如低版本的 ie。chrome 和较新版本的 ie 同时支持这两种风格。

# nodejs

