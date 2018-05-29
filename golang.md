## 教程

* [tour go 中文教程](https://tour.go-zh.org/welcome/1)
* [godoc](https://godoc.org/)
* [effective go](https://golang.org/doc/effective_go.html)

## 常用 function
### 数组
```
func StringInSlice(a string, list []string) bool {
	if list == nil || len(list) == 0 {
		return false
	}

	for _, b := range list {
		if b == a {
			return true
		}
	}
	return false
}
```
### 类型转换
```
func IntToStr (input int) string {
	return strconv.Itoa(input)
}
```

### 数据库
* [pq](https://godoc.org/github.com/lib/pq) Postgres
* [mgo](https://labix.org/mgo) Mongodb
* [mysql](https://github.com/go-sql-driver/mysql)

关于连接 remote 的 mysql，使用下面的代码
```
import "database/sql"
import _ "github.com/go-sql-driver/mysql"

db, err := sql.Open("mysql", "user:password@tcp(192.168.1.1:3306)/dbname")
```
后面的一段称为 DSN (Data Source Name)，完整的格式约定如下
```
[username[:password]@][protocol[(address)]]/dbname[?param1=value1&...&paramN=valueN]
```
### WEB 框架
* [beego](https://godoc.org/github.com/astaxie/beego)
