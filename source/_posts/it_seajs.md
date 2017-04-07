---
title: 模块化开发
date: 2016-10-15 18:54:14
tags: angular
categories: 技术
---

## 概述

### 什么是模块化开发

- 将软件产品看作为一系列功能模块的组合
- 通过特定的方式实现软件所需模块的划分、管理、加载

### 为什么使用模块化开发

<!--more-->

- https://github.com/seajs/seajs/issues/547
- 协同
- 代码复用
- 解决问题
  + 大量的文件引入
  + 命名冲突
  + 文件依赖
    * 存在
    * 顺序


### 实现模块化的推演

#### step-01 全局函数



#### step-02 封装对象



#### step-03 划分私有空间



#### step-04 模块的扩展与维护



#### step-05 第三方依赖管理


在什么场景下使用模块化开发
  业务复杂
  重用逻辑非常多
  扩展性要求较高


*****

## 实现规范

### CommonJS规范

### AMD规范

### CMD规范


*****

## 实现

### Seajs

#### 使用步骤

1. 在页面中引入sea.js文件
2. 定义一个主模块文件，比如：main.js
3. 在主模块文件中通过define的方式定义一个模块，并导出公共成员
4. 在页面的行内脚本中通过seajs.use('path',fn)的方式使用模块
5. 回调函数的参数传过来的就是模块中导出的成员对象

#### 定义一个模块

- define

```javascript
define(function(require, exports, module) {
  exports.add = function(a, b) {
    return a + b;
  };
});
```

#### 使用一个模块

- seajs.use
  + 一般用于入口模块
  + 一般只会使用一次
- require
  + 模块与模块之间

#### 导出成员的方式

- module.exports
- exports.xxx
- return
- 三种方式的优先级

#### 异步加载模块

- 默认require的效果是同步的，会阻塞代码的执行，造成界面卡顿
- require.async();

```javascript
require.async('path',function(module) {

});
```

#### 使用第三方依赖（jQuery）

- 由于CMD是国产货，jquery默认不支持
- 改造

```javascript
// 适配CMD
if (typeof define === "function" && !define.amd) {
  // 当前有define函数，并且不是AMD的情况
  // jquery在新版本中如果使用AMD或CMD方式，不会去往全局挂载jquery对象
  define(function() {
    return jQuery.noConflict(true);
  });
}
```

#### Seajs配置

- [配置](https://github.com/seajs/seajs/issues/262)
- seajs.config
  + base
  + alias

#### 使用案例

- Tab标签页


### RequireJS


-------

<div  align=center>
    <center> 扫描二维码添加丁盛为你的好友</center ><center><font color=#f75000 size=>技术、户外、摄影、自驾 欢迎交流</font><center><img width='40%' align='center' src='/uploads/wechat-qcode.jpg
'>
</div>

