---
title: formdata和blob 新api学习
date: 2018-04-26 10:54:56
tags: js
---

formdata  可以使用ajax提交表单异步请求
使用直接百度参考


最近还接触了一个新的api 把二进制文件转换成 对应的文件类型


```js
// data 二进制流文件
var file = new Blob([data],{type:application/pdf});
var fileUrl = URL.createOjectURL(file);
window.open(fileUrl)

```