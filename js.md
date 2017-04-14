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
