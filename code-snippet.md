# CSS

## Reset
> css 的出现使得 html tag 本身所具备的大量外观属性成为鸡肋。因为，对于大部分希望在 web 页面上体现“性格”的开发人员来说，html tag 本身的外观是不重要的，甚至是必须要掩盖的东西。这也是为什么需要 css reset 的一个重要原因，先将 html tag 的外观属性抹掉，然后再用 css 重新装修。

下面是一些常用的 reset rule，仅供参考，推荐引用通用的 reset 脚本[1](https://meyerweb.com/eric/tools/css/reset/)[2](https://gist.github.com/DavidWells/18e73022e723037a50d6)以代替手工编写。

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

a:link 初始

a:hover 鼠标悬停时

a:active 鼠标点击时

a:visited 访问过
```

## 伪类和伪元素
伪类和伪元素不能独立存在，必须依附于某个具体的选择器相关的元素。比如：
div:hover，表示当鼠标悬停在 div 上时，选中 div。

### 伪类
伪类是选择元素的某些特殊状态，比如悬停（:hover）。

常用的有：:hover, :focus, :disabled,:nth-child,等等，这是完整的[索引](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-classes)。

:nth-child(n) 和 :nth-of-type(n) 的区别：
:nth-child(n) 选择的是父元素的第 n 个子元素。
type:nth-child(n) 选择的是父元素的第 n 个子元素，且类型必须为 type。
type:nth-of-type(n) 选择的是父元素的第 n 个类型为 type 的子元素。

不制定 type 信息的 :nth-child 规则简单，指定类型之后，从字面上看起来，和 :nth-of-type 非常像，但其实完全不同。
举个例子.
html
```html
<div>
  <span>span 1</span>
  <span>span 2</span>
  <em>em 1</em>
  <span>span 3</span>
</div>
```
css
```css
div span:nth-child(3) {
  background-color: yellow;
}
```
你会发现第三个 span 完全没有被选中。
如果换成这样：
```css
div span:nth-of-type(3) {
  background-color: yellow;
}
```
第三个 span 背景色就变黄色了。为什么这一次成功了呢? 回到最开始的定义：
>type:nth-child(n) 选择的是父元素的第 n 个子元素，且类型必须为 type。
type:nth-of-type(n) 选择的是父元素的第 n 个类型为 type 的子元素。

背后的逻辑是：span:nth-child(3) 会从四个子元素里找到第三个，发现是 em，随即丢弃。而 span:nth-of-type(3) 会先过过滤所有的 span 元素，从中查找第三个 span。

总结一下对应用的启发：如果要选择绝对位置和类型必须同时满足的，使用 type:nth-child(n)，如果只需要选择相对位置是固定的而不介意中间夹杂其他元素，则使用 type:nth-of-type(n)。

first-child,last-child 等等只是特定位置的方便方法，不多说。关于 n 的运用，比如选择奇数或偶数位置的子元素，详见 MDN 上的 [nth-child](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:nth-child).



### 伪元素

> 伪元素是一个附加至选择器末的关键词，允许你对被选择元素的特定部分修改样式。

最常见的应用是清除浮动

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

详见 MDN [Preudo Elements](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-elements)

## 其他
较少使用的 css。

### Auto complete input 样式
有时候需要隐藏 autocomplete 背景色，比如chrome默认自动填充的内容，背景色为黄色。可以使用下列 css 定制。
```css
input:-webkit-autofill,
input:-webkit-autofill:hover, 
input:-webkit-autofill:focus
input:-webkit-autofill:active {
  transition: background-color 5000s ease-in-out 0s;
}

```
### 输入选项
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


* download
```javascript
function download(text, name, type) {
  var a = document.createElement('a')
  a.style.display = "block";
  var file = new Blob([text], {type: type});
  a.href = URL.createObjectURL(file);
  a.download = name;
  document.body.appendChild(a);
  a.click();
  document.body.removeChild(a);
}
```
