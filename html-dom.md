# 自定义事件
## 基于 dom
```javascript
var event = new Event(name, eventInit);
eventTarget.dispatchEvent(event)
```
### eventInit
Is an EventInit dictionary, having the following fields:
* "bubbles": (Optional) A Boolean indicating whether the event bubbles. The default is false.
* "cancelable": (Optional) A Boolean indicating whether the event can be canceled. The default is false.
* "scoped": (Optional) A Boolean indicating whether the given event bubbles. If this value is true, deepPath will only contain a target node.
* "composed": (Optional) A Boolean indicating whether the event will trigger listeners outside of a shadow root. The default is false.

## 自定义事件系统
```javascript
var eventHub = (function Hub(){
  var listeners = {};
  
  Hub.prototype.addEventListener = function(){}
  Hub.prototype.removeEventListener = function(){}
  Hub.prototype.removeEventListeners = function(){}
})()
```

# 操作node
## 搜索
```javascript
document.getElementById
document.getElementsByClassName
document.getElementsByName
document.getElementsByTagName
document.querySelector
document.querySelectorAll
```
注意，搜索结果不止一个时，返回的是**类数组**对象
