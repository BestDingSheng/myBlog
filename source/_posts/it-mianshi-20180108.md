---
title: 收藏的js面试题
date: 2018-01-08 20:49:50
tags: 面试
---

```js
if (!("a" in window)) {
    var a = 1;
}
alert(a); 

var a = 1,
    b = function a(x) {
        x && a(--x);
    };
alert(a);  1

function a(x) {
    return x * 2;
}
var a =6;
alert(a);  

var foo = 'function '; 
var foo ;
console.log(foo);

function b(x, y, a) {
    arguments[2] = 10;
    alert(a);   
} 
b(1, 2);

function a() {
    alert(this);
}
a.call(null);   window
```

