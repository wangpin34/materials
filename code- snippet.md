# CSS

# HTML
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
* viewport
```

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
function addListener(el, envType, func){
  if(!el) throw new Error('No element provided');
  
  (el.addEventListener || el.attachEvent)(envType, function(event){
    func(event||window.event)
  })
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
