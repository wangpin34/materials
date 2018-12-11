# 全栈工程师学习资料

## 规范（spec/rec）
* https://blog.whatwg.org/
* https://dom.spec.whatwg.org/
* https://html.spec.whatwg.org/

## 社区
独学而无友，则孤陋而寡闻。
* [stackoverflow](http://stackoverflow.com/)
* [前端网](http://www.w3cfuns.com/portal.php)
* [cnode](https://cnodejs.org/) [网站代码](https://github.com/cnodejs/nodeclub/)
* [nodejs 中文社区](http://www.nodejs.net/)
* [segmentfault](http://segmentfault.com/)

## 在线学习
* [w3school](http://www.w3school.com.cn/index.html)
* [codesandbox](https://codesandbox.io)

## 热门博客
排名不分先后
* [阮一峰的网络日志](http://www.ruanyifeng.com/blog/)
* [玉伯 lifesinger](https://github.com/lifesinger/lifesinger.github.io/issues)
* [粉丝日志](http://blog.fens.me/)
* [掌心](http://www.zhanxin.info/)
* [云路](http://www.iyunlu.com/view/)
* [张云龙](https://github.com/fouber/blog)
* [邱俊涛 I code it](http://icodeit.org/)
* [lucida](http://zh.lucida.me/blog)
* [司徒正美](http://www.cnblogs.com/rubylouvre/)
* [淘宝 ued](http://ued.taobao.org/blog/)
* [张鑫旭](http://www.zhangxinxu.com/)
* [QUQU](https://imququ.com/)

## 学习资料

### 基础知识
* [ES6 入门](http://es6.ruanyifeng.com/)
* [eloquent javascript | 雄辩的 javascript ](http://eloquentjavascript.net/)
* [it-ebooks](http://www.it-ebooks.info/) Most books are not available
* [CSS.Secrets](https://res.wisedu.com/FS/%E5%89%8D%E7%AB%AF%E5%85%A5%E9%97%A8/3.%20CSS.Secrets.Better.Solutions.to.Everyday.Web.Design.Problems.pdf)
* [google js style](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)
* [google web fundamentals](https://developers.google.com/web/fundamentals/)
* [status code 定义](http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html)

### 数据库
* [sequelzie](http://sequelize.readthedocs.org/en/latest/) sequelize是成熟的orm框架。

### 单元测试
* [Testing With Mocha, Sinon.js & Mocking Request](http://bulkan-evcimen.com/testing_with_mocha_sinon)
* [node 单元测试入门](http://blog.csdn.net/wp270280522/article/details/48734409) 鄙人写的小文章
* [sinon](http://sinonjs.org/docs/) 用于在测试中模拟数据库，http和任何你想要模拟的函数
* [chai](http://chaijs.com/) 简单好用的断言库

### nodejs
* [node 7天教程](http://www.lvtao.net/content/book/node.js.htm)
* [node 从零开始系列文章] (http://blog.fens.me/series-nodejs/)
* [best practices](http://www.innofied.com/node-js-best-practices/)
* [创建模块共享的常量](http://stackoverflow.com/questions/8595509/how-do-you-share-constants-in-nodejs-modules)
  
  个人比较推荐这种方式
  ```
  module.exports = Object.freeze({
    MY_CONSTANT: 'some value',
    ANOTHER_CONSTANT: 'another value'
  });
  ```
  在其他模块使用：
  ```
  var constants = require('./constants');

  console.log(constants.MY_CONSTANT); // 'some value'

  constants.MY_CONSTANT = 'some other value';

  console.log(constants.MY_CONSTANT); // 'some value'
  ```

## 开发应用

### 前端组件相关
* [react](https://facebook.github.io/react/)
* [vue](https://github.com/vuejs/vue)
* [angular](https://github.com/angular/angular)
* [react-native](https://facebook.github.io/react-native/)
* [redux](http://redux.js.org/docs/introduction/)
* [Rxjs](https://github.com/Reactive-Extensions/RxJS)

### web框架
* [Express](http://expressjs.com/)
* [Koa](https://github.com/koajs/koa)

### 移动端
* [kotlin lang](https://kotlinlang.org/docs/tutorials/android-frameworks.html)

### html模板
* [jade](http://jade-lang.com/reference/) 由于商标问题， jade 已经改名为 pug
* [pug]
* ejs

### UI
* [jquery UI](http://jqueryui.com/)


### Spring
* [tools](https://spring.io/tools/sts/all)
* [rest service](https://spring.io/guides/gs/rest-service/#initial)
* [spring boot](https://projects.spring.io/spring-boot/#quick-start)
* [cli](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#getting-started-installing-the-cli) 
* [springfox](http://springfox.github.io/springfox/docs/current/#introduction)

## 拓展

### 设计
* [Material Design](https://material.io/guidelines/#)
* [Dribbble](https://dribbble.com/)
* [Huaban](http://huaban.com/)

### 浏览器
* [Chromium](https://www.chromium.org/Home)

### 显示文档，图片
* [如何在浏览器中显示word文档](http://stackoverflow.com/questions/9418850/how-to-display-a-word-document-using-fancybox)

### 优化

* ***前端优化是一个循序渐进的过程***。
* ***只要适合当前技术和业务的优化方案，就是好的方案***。

### 架构
* [理解RESTful架构](http://www.ruanyifeng.com/blog/2011/09/restful)

### 网络
* [不同网段的访问问题](http://networkengineering.stackexchange.com/questions/10530/ping-between-different-subnet-across-a-link)

### 算法

### 操作系统
* [鸟哥linux基础篇](http://vbird.dic.ksu.edu.tw/linux_basic/linux_basic.php)
* [鸟哥linux服务器篇](http://vbird.dic.ksu.edu.tw/linux_server/)


