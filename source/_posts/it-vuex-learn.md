---
title: vuex理解
date: 2017-07-09 21:26:07
tags: vue
---

![](https://vuex.vuejs.org/zh-cn/images/vuex.png)

<!--more-->

-------
> 之前使用vuex一直都是半懂半不懂的今天系统的了解了下vuex终于理解差不多了下面分享下个人理解


### vuex是什么？
vuex是一个状态管理器把所有状态都存在store这个容器里面

### vuex能做什么？
vuex能够很好的解决组件中的通信，让数据更清晰明了，更容易管理。

### vuex怎么使用？
1 安装
```
npm install vuex --save
```
2 在一个模块化的打包系统中，您必须显式地通过 Vue.use() 来安装 Vuex：
```js
import Vue from 'vue';
import Vuex from 'vuex';
Vue.use(Vuex);
import state from './state';
import actions from './actions';
import mutations from './mutations';
import getters from './getters';
export default new Vuex.Store({
  state, actions, mutations, getters
})


```
3 在路口文件main.js中引入 store
```js
import stroe from './store'
new Vue({
  el: '#app',
  router,
  store, //main.js注入store
  template: '<App/>',
  components: { App }
})

```
项目store目录下的文件index为store注入vue文件
```shell
.
├── actions.js
├── getters.js
├── index.js
├── mutations.js
├── state.js
└── types.js

0 directories, 6 files

```
##  重点来了
state.js文件存放store中的数据字段
getters.js文件存在获取store.state的方法,
mutations.js文件存放修改state的方法 mutations是同步操作
actions.js存放异步操作state方法，在vuex中只有mutations才能修改state actions还是调用的mutations

mapGetrers,mapActions 是两个常用的vuex辅助函数

在组件中如何使用 

```js
improt {mapGetters,mapActions} from 'vuex'

export default{
data(){
return{
}
},
computed{
...mapGetters(['xxx']),
},
methods:{
...mapActions(['xxxx'])
}

}
```



