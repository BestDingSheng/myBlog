---
title: Vue非父子组件通信方法
date: 2017-09-06 19:16:13
tags: vue
---

> 一提到两个非父子组件通信方法，有经验的 coder 肯定会说用 Vuex 啊，我个人建议不要为了用 Vuex 而用 Vuex，除非你的项目很大，耦合度很高，需要大量的储存一些 data，组件之间通信频繁。当然还是要根据自己的业务场景的来决定，总之还是那句话，不要为了用 Vuex 而用 Vuex！


 Vue 官网介绍了非父子组件通信方法：
 ![](http://upload-images.jianshu.io/upload_images/1430985-11f7e296be088d3d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/600)
 不过官网说的太简单了，新手看完估计还是一脸懵逼。还有这个空的 Vue 实例放到哪里合适也值得商榷。
  
<!--more-->
  
-------

这篇文章的目的就是用一个简单的例子让你明白如何用 Bus 🚌 来进行通信：
![](http://upload-images.jianshu.io/upload_images/1430985-6f49976b34d4e44f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/300)
假设 bb 组件里面有个按钮，点击按钮，把 123 传递给 aa 组件


```js
// 根组件（this.$root)
new Vue({
  el: '#app',
  router,
  render: h => h(App),
  data: {
   // 空的实例放到根组件下，所有的子组件都能调用
    Bus: new Vue()
  }
})
```
bb 组件内调用事件触发↓


```js
<button @click="submit">提交<button>

methods: {
   submit() {
     // 事件名字自定义，用不同的名字区别事件
      this.$root.Bus.$emit('eventName', 123)
    }
 }

```

aa 组件内调用事件接收↓

```js
  // 当前实例创建完成就监听这个事件
  created(){
    this.$root.Bus.$on('eventName', value => {
      this.print(value)
    })
  },

  methods: {
    print(value) {
      console.log(value)
    }
  },

  // 在组件销毁时别忘了解除事件绑定
  beforeDestroy() {
     this.$root.Bus.$off('eventName')
  },

```

这样就可以了，是不是很简单？
















