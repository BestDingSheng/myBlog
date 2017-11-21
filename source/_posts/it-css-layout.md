---
title: flexible.js移动端应用
date: 2017-10-30 14:31:20
tags: [css,js]
---

> flexible.js 手淘出的一款处理移动端响应式的js工具

### 下载地址
https://github.com/amfe/lib-flexible github
https://github.com/amfe/article/issues/17 作者详解

### 概略

框架整体模仿jquery,为一个立即执行函数，并对外暴露lib对象，提供rem => px，和px => rem的转化方法。当在调整窗口尺寸的时候可以重置document.documentElement的fontSize的大小。


<!--more-->

### 基本原理

通过设置meta标签的content中 initial-scale,maximum-scale,minimum-scale,的值，其值根据屏幕像素比控制，在dpr越大，屏幕渲染的画布越大。

### 框架步骤

1、判断是否存在meta[name="viewport"];
2、存在直接设置，不存在自动生成，推荐不使用;
3、通过window.devicePixelRatio获取屏幕的屏幕像素比;
4、根据屏幕的尺寸，通过document.documentElement.getBoundingClientRect().width获取屏幕宽度; 
5、设置document.documentElement.style.fontSize值; 6、设置document.body.style.fontSize ; 
7、提供一些方法;

### 重要方法解读


```js

// 自定义页面元素的fontsize，方便rem的配置
function refreshRem(){
    var width = docEl.getBoundingClientRect().width;
    //屏幕信息，屏幕宽度，bound：绑定；rect：矩形
    if (width / dpr > 640) {
        width = 640 * dpr;
    }
    var rem = width / 10;
    docEl.style.fontSize = rem + 'px';
    flexible.rem = win.rem = rem;
}
   
/**
 * 对于设计稿为320px的，根元素fontsize = 32px;
 * 对于设计稿为1080px的，根元素fontsize = 108px;
 * 设屏幕的宽度为w(rem*10),设计稿尺寸为w,那么有比例关系w:rem*10 = x:1 ;
 * ==> x= w/(rem*10);（单位）
 * 那么任意设计稿尺寸 L 转化为相应的尺寸就为：L/x = (L*rem*10)/w;
 * 由于rem设置给根元素了，那么所有的尺寸均可以用rem单位来操作;
 * xrem = (L*rem*10)/w*fontsize = (L*10)/w;
 * 那么在设计稿中量取 L长度的，在编辑器中就为(L*10/w) rem;
 * 如此便完成了rem的自动适配
 */ 
```


### 换成rem公式 

100*100 div 在320的设计稿

100/320*10 = 3.125 rem


