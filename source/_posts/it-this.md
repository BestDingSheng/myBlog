---
title: javascript this学习之路
date: 2017-04-10 16:26:00
tags: [javascript]
---
> this是javascript的核心之一，this的指向之前都是一知半解不是很了解，今天看了简书上看了篇文章对js中this讲的很清楚，后面我简单的分享下我的学习笔记

javascript this的指向是面试中必问的问题，之前在百度上看this相关的文章都是写的很高深莫测，看完和没看一样 。今天的笔记参考这篇文章->[全方位解读this](http://www.jianshu.com/p/d647aa6d1ae6) 感觉本文作者让我对this有个新的认识

<!--more-->

案例1

```javascript
var a = 10;
var obj = {
    a: 20
}

function fn () {
    console.log(this.a); // fn() == window.fn() 这里this指向window
}

fn(); // 10
fn.call(obj); // 20  call 可以改变this指向 这里this指向obj
```
**在一个函数上下文中，this由调用者提供，由调用函数的方式来决定。如果调用者函数，被某一个对象所拥有，那么该函数在调用时，内部的this指向该对象。如果函数独立调用，那么该函数内部的this，则指向undefined。但是在非严格模式中，当this指向undefined时，它会被自动指向全局对象。**

案例2

```javascript
var a = 20;
var obj = {
    a: 10,
    c: this.a + 20,
    fn: function () {
        return this.a;
    }
}

console.log(obj.c);  // 40 obj.c 不是一个函数 这里的this指向window
console.log(obj.fn()); // 10 fn被obj拥有 this指向obj
```
**当obj在全局声明时，无论obj.c在什么地方调用，这里的this都指向全局对象，而当obj在函数环境中声明时，这个this指向undefined，在非严格模式下，会自动转向全局对象。可运行下面的例子查看区别。**

多来几个案列熟练下


```js
var a = 20;
var foo = {
    a: 10,
    getA: function () {
        return this.a;
    }
}
console.log(foo.getA()); // 10

var test = foo.getA;
console.log(test());  // 20
```
`foo.getA()`中，getA是调用者，他不是独立调用，被对象foo所拥有，因此它的this指向了foo。而`test()`作为调用者，尽管他与foo.getA的引用相同，但是它是独立调用的，因此this指向undefined，在非严格模式，自动转向全局window。

下面两个案列看看

```js
var a = 20;
function getA() {
    return this.a;
}
var foo = {
    a: 10,
    getA: getA
}
console.log(foo.getA());  // 10
```

```js
function foo() {
    console.log(this.a)
}

function active(fn) {
    fn(); // 真实调用者，为独立调用
}

var a = 20;
var obj = {
    a: 10,
    getA: foo
}

active(obj.getA); //20 这里this没有被拥有 this指向window
```

-------


<div  align=center>
    <center> 扫描二维码添加丁盛为你的好友</center ><center><font color=#f75000 size=>技术、户外、摄影、自驾 欢迎交流</font><center><img width='40%' align='center' src='/uploads/wechat-qcode.jpg
'>
</div>



