# CSS
## 常用 Reset
* html 和 body 的宽高， body默认的外边距
```css
html,body {
 width: 100%;
 height: 100%;
}

body {
 margin: 0;
}

```
* ol,ul 默认的内边距
```css
ol,ul {
  padding-left: 0;
}
```

* li元素默认图标
```css
li {
 list-style: none;
}
```
* a元素默认样式
```css
a {
text-decoration:none; //去掉下划线
}

//四个伪类
a:link 初始

a:hover 鼠标悬停时

a:active 鼠标点击时

a:visited 访问过
```

## 高阶选择器
* n-th
```css
//注意索引从1开始
span:first-child 选取第一个
span:last-child 选取第一个
span:nth-child(1) 选取第一个
span:nth-child(0n+1) 选取第一个
span:nth-child(odd) 选取索引为奇数的
span:nth-child(even) 选取索引为偶数的
span:nth-child(2n) 选取索引为偶数的
span:nth-child(-n+3) 选取符合-n+3 表达式的

注意以上选择器并不严格选择第n个span，如果要严格选择，请用下面的方式
span:nth-of-type(n)
span:first-of-type
span:last-of-type
```
* focus / not / ...

更详细的介绍 [MDN - Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)

## 伪元素

* after 和 before

利用 after 清除浮动
```css
div:after {
  clear:both;
  content:'.';
  display:block;
  width: 0;
  height: 0;
  visibility:hidden;
}
```

## Auto complete input 样式
有时候需要隐藏 autocomplete 背景色（极少）。
```css
input:-webkit-autofill,
input:-webkit-autofill:hover, 
input:-webkit-autofill:focus
input:-webkit-autofill:active {
  transition: background-color 5000s ease-in-out 0s;
}

```


## 其他
```css
caret-color： red；  //输入框光标颜色

//选中文字的颜色
::-moz-selection { /* Code for Firefox */
  color: red;
  background: yellow;
}

::selection {
  color: red; 
  background: yellow;
}
```

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
<meta name="viewport" content="width=device-width, initial-scale=1,maximum-scale=1.0, shrink-to-fit=no, user-scalable=no" />
<meta name="apple-mobile-web-app-capable" content="yes" />
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
<script type="text/javascript">
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
    element.attachEvent('on' + eType, function(event){
     listener&&listener(event||window.event);
    })
  }
}
```
ie 9 开始支持标准方式 [addEventListener](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)

:blush: attachEvent/detachEvent 方式仅 ie6-10 支持。 [查看兼容性](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/attachEvent)

:warning: 上面的代码虽然屏蔽了老版本 ie 和其他浏览器的差异，但是带来了一个问题，如何删除注册的 listener? 直接去删除 listener 实际上并无效果
```
var func = function(){};
addListenern(dom, func);
dom.removeEventListener(func)
```
因为真实注册的 listener 是一个外界不可知的匿名函数。那么，将这个匿名还是作为返回值交给外部，作为删除时的依据，可以吗？
答案当然是可以，但是很丑陋。借用一下 jquery 的做法，我重新实现了一个更强大的 listener 管理，并使用到 [vue-scroll](https://github.com/wangpin34/vue-scroll/blob/2.0-compatible/lib/vue-scroll.js#L22~L96) 中。完整的代码记录在 [My Gist - Q](https://gist.github.com/wangpin34/e50bc75bc0e6c25dac9427d796b710dc)

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


