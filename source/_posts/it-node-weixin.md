---
title: node开发微信公众号初体验
date: 2017-11-20 16:13:38
tags: node
---

### 微信公众号 

官网 https://mp.weixin.qq.com/ 

### ngrok

ngrok  https://ngrok.com/

用于微信调试转发内网到外网能访问

<!--more-->

### node代码

app.js

```js
var express = require("express");
var path=require('path');
var app = express();
server  = require('http').Server(app);
app.set('views',__dirname);    // 设置视图
app.set('view engine', 'html');
app.engine( '.html', require( 'ejs' ).__express );
require('./index')(app);      //路由配置文件
server.listen(1234,function(){
    console.log('App start,port 80.');
});


```

index.js 回复消息 

```js
var sha1 = require("sha1");
var xml = require("node-xml");

module.exports = function(app) {
  app.get("/", function(req, res) {
    res.render("test", { issuccess: "success" });
  });
  app.get("/interface", function(req, res) {
    var token = "weixin";
    var signature = req.query.signature;
    var timestamp = req.query.timestamp;
    var echostr = req.query.echostr;
    var nonce = req.query.nonce;

    var oriArray = new Array();
    oriArray[0] = nonce;
    oriArray[1] = timestamp;
    oriArray[2] = token;
    oriArray.sort();

    var original = oriArray.join("");

    var scyptoString = sha1(original);

    if (signature == scyptoString) {
      //验证成功
      res.send(echostr);
      console.log("hah");
    } else {
      //验证失败
      console.log("xixiix");
    }
  });
  app.post("/interface", function(req, res) {
    var post_data = "";
    req.on("data", function(data) {
      post_data = data;
    });
    req.on("end", function() {
      var xmlStr = post_data.toString("utf-8", 0, post_data.length);
      //解析消息代码
      //回发消息代码

      // 定义解析存储变量
      var ToUserName = "";
      var FromUserName = "";
      var CreateTime = "";
      var MsgType = "";
      var Content = "";
      var tempName = "";
      //开始解析消息
      var parse = new xml.SaxParser(function(cb) {
        cb.onStartElementNS(function(elem, attra, prefix, uri, namespaces) {
          tempName = elem;
        });
        cb.onCharacters(function(chars) {
          chars = chars.replace(/(^\s*)|(\s*$)/g, "");
          if (tempName == "CreateTime") {
            CreateTime = chars;
          }
        });
        cb.onCdata(function(cdata) {
          if (tempName == "ToUserName") {
            ToUserName = cdata;
          } else if (tempName == "FromUserName") {
            FromUserName = cdata;
          } else if (tempName == "MsgType") {
            MsgType = cdata;
          } else if (tempName == "Content") {
            Content = cdata;
          }
          console.log(tempName + ":" + cdata);
        });
        cb.onEndElementNS(function(elem, prefix, uri) {
          tempName = "";
        });
        cb.onEndDocument(function() {
          //按收到的消息格式回复消息
        });
      });
      parse.parseString(xmlStr);

      CreateTime=parseInt(new Date().getTime() / 1000);
      var msg="";
      if(MsgType=="text"){
         msg="谢谢关注,你说的是:"+Content;
         //组织返回的数据包
         var sendMessage=`
                 <xml>
                  <ToUserName><![CDATA[${FromUserName}]]></ToUserName>
                  <FromUserName><![CDATA[${ToUserName}]]></FromUserName>
                  <CreateTime>${CreateTime}</CreateTime>
                  <MsgType><![CDATA[text]]></MsgType>
                  <Content><![CDATA[${msg}]]></Content>
              </xml>`;
          res.send(sendMessage);
      }




    });
  });
};

```

test.html

```Html
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title>汇智网</title>
 </head>
<body>
<div><%=issuccess%></div>
</body>
</html>

```


node app.js


