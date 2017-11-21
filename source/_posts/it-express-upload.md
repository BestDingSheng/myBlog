---
title: Express中如何上传文件
date: 2017-09-11 16:09:13
tags: [node,后台]
---

在Express中我们上传图片使用[Multer](https://github.com/expressjs/multer)中间件

下面直接展示代码

前端直接使用form表单上传 需要注意的是 在上传文件的时候，表单需要加上 enctype="multipart/form-data" 属性 不加默认的话只能上传文件名

```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <title>上传文件</title>
</head>

<body>
  <form class="" action="http://localhost:9090/upload" method="post" enctype="multipart/form-data">
    <input type="file" name="file" value="">
    <input type="submit" name="" value="上传文件">
  </form>
</body>

</html>

```
<!--more-->

下面是后台nodejs代码, multer详细API请看文档 

```js

const express = require('express');
let app =express();
let multer  = require('multer');
let upload = multer({ dest: 'uploads/' });
let fs = require('fs');
app.listen(9090);

app.post('/upload',upload.any(),function(req,res){

  let result =req.files[0].destination + req.files[0].originalname;
  let pathLib = req.files[0].path;
  fs.rename(pathLib,result,function(err){
      if(err){
        res.send('上传失败');
        res.end();
      }else{
        res.send('上传成功');
        res.end();
      }
  })


})

```





