---
title: Express中如何使用模板引擎
date: 2017-09-11 16:38:00
tags: [node,后台]
---

[先来看看官网介绍](http://www.expressjs.com.cn/guide/using-template-engines.html)

> 和 Express 兼容的模板引擎，比如 Jade，通过 res.render() 调用其导出方法 __express(filePath, options, callback) 渲染模板。

> 有一些模板引擎不遵循这种约定，Consolidate.js 能将 Node 中所有流行的模板引擎映射为这种约定，这样就可以和 Express 无缝衔接。

在这里我们使用官网推荐的Consolidate.js

在根目录下有个views文件里面专门放需要编译的模板引擎

```html
<!--1.ejs-->
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
  </head>
  <body>
    我的名字叫：<%= name %>
  </body>
</html>

```
<!--more-->

重点在下面 

``` js

const express = require('express');
const consolidate=require('consolidate');
let server = express();

//输出什么东西
server.set('view engine', 'html');
//模板文件放在哪儿
server.set('views', './views');
//哪种模板引擎
server.engine('html', consolidate.ejs);

//接收用户请求
server.get('/index', function (req, res){
  res.render('1.ejs', {name: 'blue'});
});



server.listen(9090);


```

