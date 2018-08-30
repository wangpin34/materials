## 数组操作
* 去除重复元素
```javascript
array.filter(function(value, index){
  return array.indexOf(value) !== index;
})
```
* 数组差集
```javascript
array1.filter(function(value, index){
 return !array2.includes(value);
})
```

* 将第二个数组中元素插入第一个数组，注意不能给第一个数组重新赋值(不能使用 concat)
```javascript
var length = Array.prototype.push.apply(array1, array2); //返回值是array1的*新*长度
```

* 类数组对象转化为数组
类数组对象 nodelist / arguments
```javascript
nodelist = Array.prototype.slice.call(nodelist, 0);
```
## url 处理
* 获取页面 url 的 query 参数
```javascript
function getParameterByName(name, url) {
    if (!url) url = window.location.href;
    name = name.replace(/[\[\]]/g, '\\$&');
    var regex = new RegExp('[?&]' + name + '(=([^&#]*)|&|#|$)'),
        results = regex.exec(url);
    if (!results) return null;
    if (!results[2]) return '';
    return decodeURIComponent(results[2].replace(/\+/g, ' '));
}

//usage
// query string: ?foo=lorem&bar=&baz
var foo = getParameterByName('foo'); // "lorem"
var bar = getParameterByName('bar'); // "" (present with empty value)
var baz = getParameterByName('baz'); // "" (present with no value)
var qux = getParameterByName('qux'); // null (absent)
```
来源:[https://stackoverflow.com/questions/901115/how-can-i-get-query-string-values-in-javascript](https://stackoverflow.com/questions/901115/how-can-i-get-query-string-values-in-javascript)

## 禁用浏览器 Action

* 禁用拖拽文件在浏览器打开
```
  //Disable dropped file from opening in window
  //https://github.com/electron/electron/issues/908
  document.addEventListener('drop', function(e) {
    e.preventDefault();
    e.stopPropagation();
  });
  document.addEventListener('dragover', function(e) {
    e.preventDefault();
    e.stopPropagation();
  });
```
* 关闭 context menu
```
  //Disable context menu
  document.addEventListener('contextmenu', event => {
    event.preventDefault();
    event.stopPropagation();
  });
```
* 禁止双击选中
```
  //Disable double click selection
  document.addEventListener('mousedown', e => {
    e.preventDefault();
  })
```
