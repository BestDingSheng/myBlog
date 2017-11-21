---
title: Express中cookie使用
date: 2017-09-06 09:16:13
tags: [node]
---

cookie 和 session 是我们在开发中经常用到的 你真的了解吗？

| 区别 | cookie | session |
| --- | --- | --- |
| 大小 | 4k  |  无限 |
| 储存位置 | 浏览器 | 服务器 |
| 安全级别 | 不安全 | 安全 |


服务端如何向浏览器发送cookie，以express为例
[发送cookie](http://www.expressjs.com.cn/4x/api.html#res.cookie)

```js
const express = require('express');
const app = express();
app.get('/',function(req,res){
    res.cookie('name':'dingsheng')  // 发送cookie
   //  如需要添加参数 请查看官网文档    

})
```
**那么如何读取呢**
读取cookie需要用到 中间件cookie-parser
首先需要去安装 npm install cookie-parser
[获取cookie](http://www.expressjs.com.cn/4x/api.html#req.cookies)

```js
const express = require('express');
var cookieParser = require('cookie-parser')
let app = express();
app.use(cookieParser())
app.listen(9090);

app.get('/',function(req,res){
  //  获取cookies  需要使用 var cookieParser = require('cookie-parser')
  console.log(req.cookies);
  res.send(req.cookies);
})

```












