---
title: AngularJS 过滤器、服务、路由
date: 2016-10-15 18:54:14
tags: angular
comments: true
type: "tags"
categories: Testing
---


## TODOMVC案例

- 根据界面原型抽象数据成员（有哪些数据，每个数据的类型和结构）
- 设计模块，控制器
- 完成数据绑定
- 编写交互逻辑

## 过滤器

### data 过滤器

- 用于时间日期格式化

<!--more-->

### lowercase, uppercase

- 英文字符大小写转换

### number

- 数字格式化，例如将10000 → 10,000.00

### limitTo 过滤器

- 限制数量，限制字符串或者遍历长度

### orderBy

- 按照特定字段排序，默认是正序，倒序则加上-号

### filter 过滤器

- 检索特定内容，默认模糊匹配
- 如果传入对象则匹配特定属性，如传入{name:'张三'}，则匹配那么属性中包含张三

#### 自定义比较

- 默认filter过滤器使用的是模糊匹配
- 需要自定义比较函数
- filter的第三个参数


## 服务

### 内置服务

#### $log服务

- 打印控制台日志
- 启用或者关闭

#### $timeout

### 自定义服务



## 路由

### NG 中路由是单独提供的功能模块 ngRoute, 也是一个单独发型的文件

- 安装或者下载angular-route的包
- 引入这个包
- 在自己的模块中添加 ngRoute 依赖
- 路由配置（配置路由规则）
  + 规则指的就是 什么样的请求 找什么控制器
  + [{url:'/sdf',controller:'MainController'}]
- 编写对应的控制器和视图


/students/zhangsan

/:role/:name

{role:students,name:zhangsan}


## 如果连入第三方文件时不写协议的话：
http://apps.bdimg.com/libs/angular.js/1.4.7/angular.min.js
↓
<script src="//apps.bdimg.com/libs/angular.js/1.4.7/angular.min.js"></script>
如果当前你的网站是HTTP的方式部署的话，请求
http://apps.bdimg.com/libs/angular.js/1.4.7/angular.min.js
如果是HTTPS的话，请求
https://apps.bdimg.com/libs/angular.js/1.4.7/angular.min.js