---
title: 学习javascript运行原理
date: 2018-01-19 10:05:30
tags: js
---

首先记住两点

* js是单线程语言
* js的运行机制就是EventLoop事件循环机制

上代码

```js
console.log(1)
setTimeout(
    function() {
        console.log(2)
    }, 0)
console.log(3)
```
<!-- more -->
上面代码会输出什么

1 3 2 为什么呢？

js会分同步和异步队列，哪些代码会进入异步队列呢
定时器 setTimeout dom事件 ajax 还有 promise

js代码是从上到下一行一行的往下面执行，当碰到同步代码的时候回直接执行,碰到异步代码的时候会先把异步代码放到异步队列，然后接下往下执行，当没有同步代码的时候才会去执行异步代码所以这案例是输出 1 3 2

在来段代码 

```js

setTimeout(()=>{
	console.log('hhhh');
},0)

new Promise(function(reslove){
	console.log(111);
	reslove()
}).then(()=>{
	console.log(222)
})

console.log('dddd')

```
按照之前的原理我们来分析下会输出什么
这里说下 Promise的then才是异步代码 
一行一行执行 碰到setTimeout放到异步队列
new Promies 执行 111 then 里面的回调放到异步队列
console.log('dddd') 同步代码直接执行
同步代码执行完了 现在回到异步队列 按理说应该是先执行 setTimeou在执行then的回调 这么分析的话就是输出
111 ddd hhhh 222
运行了下代码结果是输出 111 ddd 222 hhhh 为啥呢？
我个人理解在异步队列中定时器的优先级是最低的 所以先执行then回调在执行定时器


当同步队列的代码没有执行完是进入不了异步队列的，来段代码


```js
setTimeout(()=>{
	console.log(1)
},1000)

while(true){
	console.log(222)
}
```
过一秒输出1吗 很多人会对setTimeout不理解以为会输出 
其实答案是不会 因为我们在上面讲过异步代码必须要在同步代码执行完才能去执行 这里 while true 一直会执行根本进入不到异步队列所以1不会输出






