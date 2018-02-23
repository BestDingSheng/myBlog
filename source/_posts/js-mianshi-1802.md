---
layout: it
title: js语言精粹2笔记
date: 2018-01-02 14:37:33
tags: js
---


案例一

```js
var obj = {
	user :'zhengzheng.zx',
	getname:function(){
		return  user;
	}
}
var getnamefn=obj.getname;
console.log(getnamefn())  // user is not defined
console.log(obj.getname())
```
<!-- more -->

 案例二

``` js
if(!("username" in window)){
	var username="hahh";
}
console.log(username);   // 变量提升  undefined 
```

案例三

```js
var obj = {
	user :'zhengzheng.zx',
	getname:function(){
		return this.user;
	}
}
var getnamefn=obj.getname;
console.log(getnamefn())  //  window.getnamefn   thsi = winodw
console.log(obj.getname())  //  this=obj
```

案列四

 原型对象是什么？
在javascript中 没定义一个对象 函数时 对象中都会包含一些预定义的属性 其中函数对象的一个属性就是原型对象的属性prototype 普通对象没有prototype属性 担有__proto__ 属性 

```js
function f1(){} 
console.log(typeof f1.prototype)   // object
console.log(typeof Function.prototype)  //function
console.log(typeof Object.prototype)  //object
console.log(typeof Function.prototype.prototype)  //undefined
```

原型对象有什么用？
1面向对象开发类的继承

```js
function Person(name){
	this.name=name;
}
Person.prototype.getName = function(){
	return this.name;
}
var hah = new Person('丁盛');
console.log(hah.getName())

```
 构造函数
 
* 	使用new关键字调用的函数
* 	构造函数可以实例化一个对象
* 	返回值 默认返回类的实例

特殊情况

* 	没有返回值
* 	简单数据类型
* 	对象类型

```js
function People(name,age){
	this.name = name ;
	this.age = age;
}
var people = new People('dingsheng',20);
console.log(people);
```

原型链是如何实现的？
1每一个函数都有一个prototype的对象属性
2每一个对象都会有一个__proto__属性，这个属性指向父类的prototype对象

原型对象中的constructor？
每个原型对象prototype中都有一个constructor属性默认指向函数本身。

```js
Person.prototype.construtor = Person;
Function.prototype.construtor = Function ;
Object.prototype.construtor=Object;
Object.construtor=Function;
```

练习题

```js
function make(num){
	return function(){
		return num;
	}
}
var arr = [make(0),make(1),make(2)];
console.log(arr[0]())
console.log(arr[1]())
console.log(arr[2]())
console.log(arr[0]())
```

练习题2
 要点this属性优先访问 原型链集成顺序先从本身实例开始访问在到原型链；

``` js
var name = 'global';
function A(name){
	alert(name);
	this.name = name;
	var name = '1';
}
A.prototype.name='2';
var a = new A('3');
alert(a.name);
delete a.name;
alert(a.name);
```

 练习三

```js
function fun(n,o){
	console.log(o);
	return {
		fun:function(m){
			return fun(m,n)
		}
	}
}

var a = function(0);
a.fun(1);
a.fun(2);
var b = fun(0).fun(1).fun(2).fun(3);
var c = fun(0).fun(1);
c.fun(2);
c.fun(3);

```

