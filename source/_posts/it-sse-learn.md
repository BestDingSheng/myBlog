---
title: 数据推送SSE学习笔记
date: 2018-01-26 10:51:20
tags: js
---
>SSE （ Server-sent Events ）是 WebSocket 的一种轻量代替方案，使用 HTTP 协议。
严格地说，HTTP 协议是没有办法做服务器推送的，但是当服务器向客户端声明接下来要发送流信息时，客户端就会保持连接打开，SSE 使用的就是这种原理。

<!-- more -->

### SSE能做什么
理论上， SSE 和 WebSocket 做的是同一件事情。当你需要用新数据局部更新网络应用时，SSE 可以做到不需要用户执行任何操作，便可以完成。

举例我们要做一个统计系统的管理后台，我们想知道统计数据的实时情况。类似这种更新频繁、 低延迟的场景，SSE 可以完全满足。

其他一些应用场景：例如邮箱服务的新邮件提醒，微博的新消息推送、管理后台的一些操作 实时同步等，SSE 都是不错的选择。

### SSE vs. WebSocket

SSE 是单向通道，只能服务器向客户端发送消息，如果客户端需要向服务器发送消息，则需要一个新的 HTTP 请求。 这对比 WebSocket 的双工通道来说，会有更大的开销。这么一来的话就会存在一个「什么时候才需要关心这个差异？」的问题，如果平均每秒会向服务器发送一次消息的话，那应该选择 WebSocket。如果一分钟仅 5 - 6 次的话，其实这个差异并不大。

在浏览器兼容方面，两者差不多。在较早之前，每当需要建立双向 Socket 时就会使用 Flash，在 移动浏览器不支持 Flash 的情况下，WebSocket 的兼容是比较难做的。

SSE 我认为最大的优势是便利：

* 实现一个完整的服务仅需要少量的代码；
* 可以在现有的服务中使用，不需要启动一个新的服务；
* 可以用任何一种服务端语言中使用；
* 基于 HTTP ／ HTTPS 协议，可以直接运行于现有的代理服务器和认证技术。
* 有了这些优势，在选择使用 SSE 时就已经为自己的项目节约了不少成本。

### demo

服务器 data.php
这里注意一点必须要\n\n结束

```php
<?php

header("Content-Type:text/event-stream;charset=utf-8");
header('Access-Control-Allow-Origin:http://127.0.0.1:8888');
echo "data:现在北京时间是".date('H:i:s')."\n\n";
 ?>

```

客户端 浏览器

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
  <script>

  var source;
  function init(){
    source = new EventSource('http://127.0.0.1:8888/SSE/data.php');
    source.onopen=function(){
      console.log('连接已建立',this.readyState)
    }
    source.onmessage=function(event){
      console.log('从服务器适时获取数据',event.data);
    }
    source.onerror=function(){

    }
  }
  init()
  </script>
</body>
</html>
```



### 参考资料
https://www.v2ex.com/t/379577


