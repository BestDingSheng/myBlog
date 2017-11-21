---
title: php学习笔记
date: 2017-06-08 21:03:44
tags: [php,后台]
---

### hellow world

```php
# php的运行环境
<?php
// 定义变量
$str = 'hellow';
# echo 像浏览器输出信息
echo $str. 'world'
// . 在php里面是连接符
?>
```
<!--more-->

### php时间

```php
time() 这个函数获取时间戳
// 时间戳并不是我们想要的 转换为具体日期
date("Y-m-d H:i:s", time())

```
使用 date() 这个系统函数，可以将时间戳格式化成任何你想要的格式。
YmdHis 都是什么意思呢？
Y 代表4位数的年份，比如 2016
y 代表2位数的年份，比如 16
m 月
d 日
H 时
i 分
s 秒

### 链接数据库

```php
$db = new mysqli('localhost', 'root', '123456', 'sodevel');

$db 对象，所有后续操作都基于该对象。

mysqli 扩展内置的类，我们拿来就用，具体的属性和方法要看手册。
localhost 数据库的IP地址，这个代表本机
root 连接账号
123456 连接密码
sodevel 要连接的数据库名称
```
判断连接是否成功


```php
if( $db->connect_errno > 0 ){
    echo "错误码：".$mysqli->connect_errno;
    echo "提示语：".$mysqli->connect_error;
    exit;
}

$db->connect_errno 错误代码，无错误的话 = 0
$mysqli->connect_error 错误信息，出错问题的文字说明
```

### 执行数据库查询

```php
$is = $db->query("SQL语句");

$db 上一节连接数据库后得到的对象
query() 执行对象中的方法。
SQL语句，计划让数据库执行的命令语句

$is 在增删改的操作中，得到一个 布尔值，true 表示操作成功，false 表示操作失败。
```
### 插入乱码

```php
//定义当前连接，使用UTF8编码，你也可以使用GBK等
$db->query("SET NAMES UTF8");
```


