---
title: 正则学习笔记
date: 2018-06-04 10:12:50
tags: 正则
---

> 正则在工作中对我们帮助很大但是不经常使用又很容易忘记

正则在线工具

[www.regexper.com](http://www.regexper.com/)

### 量词


```
? 出现0次或者一次

+ 至少出现一次

{3}出现3次

{3,} 至少出现3次

{3,5}出现3到5次

* 可以出现任意次

```

<!-- more -->
### 单词边界

\bis\b 匹配is 这个单词

\d 匹配数字

正则或者用[/-] 表示或者/ -

^ 开头 $ 结尾

js 中正则表达式对象 RegExp

创建正则表达式两种方式 1 字面量 var reg = /\bis\b/ var reg =new RegExp('',/)

### 修饰符

g 全局搜索

i 忽略大小写

m 多行搜索


### 字符类

[abc] 匹配a 或者 b 或者 c

### 字符类去反

[^abc] 匹配不是 a b c

### 范围类

[a-z]匹配a到z的字母

[a-zA-Z] 匹配小写到大写的字母

2018-09-12 /[0-9-]/ 后面在加一个-可以匹配-

### 预定义类

. [^\r\n] 除了回车符合换行符之外的所有字符

\d [0-9] 数字字符

\D [^0-9] 非数字符

\s 匹配空白符

\S 非空白符

\w 配皮字母数字 下划线

\W 非单词字符

### 贪婪模式

‘12345678’.replace(/\d{3,6}/,'x') 默认正则会按最多匹配

“x78” 结果

### 非贪婪模式

尽可能少的匹配 一旦匹配成功就不在继续匹配

非贪婪模式只要在量词后面加上？即可

/\d{3,5}?/ 匹配3次

### 分组

()

### 或者

(|)

反向引用

![image](http://upload-images.jianshu.io/upload_images/4743589-0118597bed7ce757?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 忽略分组

![image](http://upload-images.jianshu.io/upload_images/4743589-de7412ef6d4b9033?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 前瞻

![image](http://upload-images.jianshu.io/upload_images/4743589-915aaa3b132ad36f?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

'a2*3'.replace(/\w(?=\d)/) 判断后面的断言

![image](http://upload-images.jianshu.io/upload_images/4743589-a470dc92963693b8?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 匹配 位置

/(?=l)/ 匹配l前面

/(?!l)/ 相反

![image](http://upload-images.jianshu.io/upload_images/4743589-47d0c8410f8432cf?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


