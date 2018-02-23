---
title: 'socket.io学习笔记'
date: 2018-01-25 17:22:38
tags: nodejs
---

即时通信当下最火的技术莫非socket了，
今天简单的看了下api写了个demo总结下
这里我们结合使用express

### 安装

npm install socket.io --save
    
下面是我们的目录结构

```tree
.
├── app.js
├── index.html
├── package.json
├── pm2.json
└── public
    ├── index.html
    ├── javascript
    │   └── socket.js
    └── style

3 directories, 6 files
```

<!-- more -->
    
主要就用到了app.js和index.html

app.js

```js
var app = require("express")();
var express = require("express");
var server = require("http").Server(app);
var io = require("socket.io")(server);
app.get("/", function(req, res) {
  res.sendFile(__dirname + "/index.html");
});

io.on("connection", function(socket) {

  socket.on("line", function(data) {
    console.log(JSON.stringify("浏览器给我发消息了" + data));
    io.sockets.emit("line", {msg:'我是广播消息'});

  });
});

server.listen(3000, function() {
  console.log("server is running");
});

```
index.html


```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
</head>
<body>
  <h1>dingsheng</h1>
  <script src="/socket.io/socket.io.js"></script>
  <script>
var socket = io.connect("http://localhost:3000/");

socket.on("connect", function() {
  console.log("与服务器连接成功");
});

socket.emit("line", { ding: "sheng" });
socket.on('line',function(data){
  console.log("服务器发来消息"+JSON.stringify(data))
})
</script>
</body>
</html>

```

### 参考资料

 https://www.bbsmax.com/A/QV5Z4lRVzy/

 http://febuild.me/socket.iodoc/#!/serverapi 
 
 https://github.com/nswbmw/N-chat 聊天室 实战





