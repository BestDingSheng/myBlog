---
title: Vue keep-alive 使用
date: 2017-07-12 07:03:34
tags: vue
---

**keep-alive是什么**
他是vuejs提供的一个组件
**keep-alive有什么用**
keep-alive可以把组件缓存起来提升用户体验减少不不必要的请求
**keep-alive怎么用**

<!--more-->

```js
<keep-alive>
  <router-view></router-view>
</keep-alive>
```
这样全部的路由都会被缓存起来切换的时候不会重新加载数据
如果想要部分路由需要加载怎么做，我们可以通过vuejs的生命周期函数


```js
    created: function () {
      console.log(1)
    },
    mounted: function () {
      console.log(2)
    },
    activated: function () {
      console.log(3)
    },
    deactivated: function () {
      console.log(4)
    },
```
当组件被使用的时候activated生命周期函数会被调用，我们只需要把我们需要重新加载的代码放在activeted钩子函数里面即可


