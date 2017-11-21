---
title: es6-module笔记
date: 2017-11-01 14:46:52
tags: js
---

http://es6.ruanyifeng.com/#docs/module 


```js

// export.js
var lastname = 'sheng'
var firstname = 'ding'
export {lastname,firstname}

// or

export var lastname = 'sheng'
export var firstname = 'ding'

```

```js

// import.js
import {lastname,firstname} from ./export.js
// 使用
console.log(lastname)
 // 导出全部
 import * as all from ./export 
// 使用
all.lastname

```

