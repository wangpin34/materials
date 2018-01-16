
## CURL
CURL 常用于调试 HTTP API。相比 Postman, Linux 平台上有更加广泛的支持，而且使用 CURL 可以观察到更加详细的信息，值得学习。

假设有以下几个 API

```
GET /v1/users
POST /v1/users
GET /v1/users/abcd-efg
PATCH /v1/users/abcd-efg
DELETE /v1/users/abcd-efg
```

上传数据类型为 application/json。对应的 curl 命令

```
curl /v1/users
curl -XPOST -H "Content-Type: application/json" -d '{"name":"wangpin"}' /v1/users 
curl /v1/users/abcd-efg
curl -XPATCH -H "Content-Type: application/json" -d '{"name":"wang pin"}' /v1/users/abcd-efg 
curl -XDELETE /v1/users/abcd-efg
```

注：*上面为了叙述方便，省略了完整 URL, 比如 http://api.com/v1/users* 。

解释一下：
* 默认使用 GET 方法。 -XPOST 表示 POST 方法，其他同理。 
* -H 表示 Header， 如果有更多的 Header，可再添加 -H 选项。
* -d 发送数据，数据的格式由 Content-Type 决定。

如果要发送Byte数据，应该使用 --data-binary 选项
  
```
--data-binary @icon.jpg
```
**@ 表示从指定文件中获取数据**。如果想要在 Header 中引入文件内容，比如我们将 token 保存在文件中，在每个 API 调用中使用。

```
curl -H "Authorization:${cat token.txt}"

```

如果要提交 Form，需要使用 -F 选项

```
-F name=wangpin -F password=123
```
表单中也可以上传文件
```
-F file=@upload.json
```

### 保存结果
可以将 API 的返回结果保存为一个文件。

```
curl -o users.json /v1/users
```

### 代理支持
如果需要代理才能够访问 API，需要手动设置代理（curl并不会参考环境变量 HTTP_PROXY 等）。

```
curl -x http://proxy.com /v1/users
```


## 参考资料
[Man CURL](https://curl.haxx.se/docs/manpage.html)
