---
title: instanceof&&hasOwnProperty用法
date: 2018-06-01 16:41:50
tags: js
---

>  instanceof hasOwnProperty   这个两个属性经常看到但自己没怎么用，刚好今天闲了下来仔细看了这两个属性

### instanceof

```js
var oStringObject = new String("hello world"); 
console.log(oStringObject instanceof String);   // 输出 "true"
```
```js
// 判断 foo 是否是 Foo 类的实例
function Foo(){} 
var foo = new Foo(); 
console.log(foo instanceof Foo)//true
```
instanceof  可以判断 一个对象是不是另一个对象的实例 

<!--more-->

复杂的用法看这里 https://www.ibm.com/developerworks/cn/web/1306_jiangjj_jsinstanceof/


### hasOwnProperty


```js
		function Person(){
			this.name = 'hah'
		}
		Person.prototype.say = 'ddd';
		console.log(dingsheng.hasOwnProperty('name')) // true
		console.log(dingsheng.hasOwnProperty('say')) // false
```

hasOwnProperty  可以判断某个属性是实例属性还是原型上的属性如果是实例属性那么久返回true 原型的上的属性就返回false

### hasOwnProperty的使用场景

当使用for in 遍历一个对象的时候不想去遍历到原型的属性就可以使用 hasOwnProperty

```js
		var obj = {
			a:'hh',
			b:'dd'
		}
		Object.prototype.say='hh'
		for(let item in obj){
			console.log(itme) // a b say
		}
```
分别会打印出 a b say 如果我不想遍历原型上的属性就使用hasOwnProperty判断下就行了

```js
		var obj = {
			a:'hh',
			b:'dd'
		}
		Object.prototype.say='hh'
		for(let item in obj){
			if(obj.hasOwnProperty(item)){
				console.log(itme) // a b 
			}
			
		}
```



