# HTTP 状态代码参考

HTTP 状态代码指示了 http请求的响应状态，分为5类，依次是1xx，2xx，3xx，4xx，5xx。


## 1xx

## 2xx 
2开头的表示http请求成功，常用的有如下几个：

### 200
表示请求成功，返回了请求的数据。
### 204
表示请求成功，但是并没有返回数据。可能是资源并不存在。


## 3xx

### 304 Not Modified
表示 GET 请求的资源没有被修改。常用于浏览器静态资源的缓存机制。

## 4xx
4开头表示***由于客户端的错误导致请求失败***。
### 400 Bad Request
由于请求的语法错误，导致服务器不能解析客户端的请求。
### 401 Unauthorized
客户端请求缺少用户身份证明，获取证明无效，导致服务器拒绝请求。
### 403 Forbidden
客户端的请求正确，但是后端因为某种原因禁止访问资源，并返回具体原因给客户端。如果不需要返回具体原因，应该采用 404。
### 404 Not Found
表示请求的资源并不存在。通常用于服务器端拒绝客户端请求，并且不想解释原因。
### 405 Method Not Allowed
表示对资源的请求方法不允许，返回header中应该有一个列表，包含允许的方法。
### 409 Conflict

## 5xx
5开头表示***由于服务器的错误导致请求失败***。
### 500 Internal Server Error
### 501 Not Implemented
### 502 Bad Gateway
### 503 Service Unavailable
### 504 Gateway Timeout

# 参考文献
[rfc2616/rfc2616-sec10.html](http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html)
