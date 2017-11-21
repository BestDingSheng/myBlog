---
title: node学习笔记
date: 2017-09-05 09:14:38
tags: [node,后台]
---

什么是nodejs
> Node.js是一个能够在服务器端运行JavaScript的开放源代码、跨平台JavaScript运行环境。Node.js由Node.js基金会持有和维护[3]，并与Linux基金会有合作关系[4]。Node.js采用Google开发的V8运行代码，使用事件驱动、非阻塞和异步输入输出模型等技术来提高性能，可优化应用程序的传输量和规模。这些技术通常用于数据密集的事实应用程序。

学习一门语言首先要掌握如何愉快的输出hello world 

```js
var http = require('http');
var server = http.createServer(function(req,res){
  console.log(res);
  res.write('hellow world');
  res.end();
})
server.listen(9090);

```
<!--more-->


这段代码复制到index.js文件中运行下面代码输入localhost:9090 即可看到hello world；
在终端中运行 

``` js
node index.js 
```

作为一个服务器肯定要能获取到浏览器的get和post参数


``` js

// 作为一个服务器肯定需要能获取到get和post参数

//  如何获取浏览器get参数
var http = require('http');
let url = require('url');
// url.parse() 方法会解析一个 URL 字符串并返回一个 URL 对象。
var server = http.createServer(function(req,res){
  let urlLib = url.parse(req.url,true);
  let GET = urlLib.query;
  // Url {
  //   protocol: null,
  //   slashes: null,
  //   auth: null,
  //   host: null,
  //   port: null,
  //   hostname: null,
  //   hash: null,
  //   search: '?act=add',
  //   query: { act: 'add' },
  //   pathname: '/index',
  //   path: '/index?act=add',
  //   href: '/index?act=add'
  // }


console.log(GET);

  res.end();
})
server.listen(9090);

```

### **node常用模块**

* http  http.createServer
* querystring qs.parse(str)
* url   url.parse(req.url,true)
* fs  fs.readFile


### **node模块化**
http://nodejs.cn/api/modules.html  文档
导出一个变量使用 export
导出一个function 使用 module.export;
**在引入模块中需要注意**
举个列子 require('http')  这种是从 node_modules文件中查找，如果是想引入 项目文件夹里面的 需要require('./http') 这样是找文件


