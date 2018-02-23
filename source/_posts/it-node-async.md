---
title: 使用Async和Await优雅的解决异步编程
date: 2018-02-02 09:59:40
tags: node
---

Async Await 是es7的东西不过node7.6以上的版本都已经支持了，
基本上使用js大多时候都是异步的，有了Async Await 就可以优雅的解决异步代码了；


### showcode


```js
async function test (){
    return "hello"
}
console.log(test()) // Promise { 'hello' }
```
async 函数返回一个return promise的值 

<!-- more -->

```js
 function test(){
  return new Promise(function(resolve, reject) {
    setTimeout(()=>{
      resolve(1)
    },1000)
  });
}

```
这段代码如果不用async怎么调用

```js
test().then((res)=>{
    console.log(res) //1 
})
```
下面是使用async和await ， 这里注意一点await要放在async函数里面使用


```js
async function fn (){
    let data = await test()
    console.log(data) // 1
}
fn()
```

使用await就能直接返回promise resolve的值不用then了可以少些很多代码



### 参考资料

https://blog.fundebug.com/2017/04/04/nodejs-async-await/

