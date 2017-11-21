---
title: vue-routet使用笔记
date: 2017-06-28 14:02:53
tags: vue
---

[vue-router中文文档](https://router.vuejs.org/zh-cn/)

### 安装 

1. cdn  
```
<script src="/path/to/vue.js"></script>
<script src="/path/to/vue-router.js"></script>
```
2. npm   
```
npm install vue-router
```

<!--more-->

如果在一个模块化工程中使用它，必须要通过 Vue.use() 明确地安装路由功能：

```js
import Vue from 'vue'
import VueRouter from 'vue-router'

Vue.use(VueRouter)
```
### 文档的例子
html

```html
<script src="https://unpkg.com/vue/dist/vue.js"></script>
<script src="https://unpkg.com/vue-router/dist/vue-router.js"></script>

<div id="app">
  <h1>Hello App!</h1>
  <p>
    <!-- 使用 router-link 组件来导航. -->
    <!-- 通过传入 `to` 属性指定链接. -->
    <!-- <router-link> 默认会被渲染成一个 `<a>` 标签 -->
    <router-link to="/foo">Go to Foo</router-link>
    <router-link to="/bar">Go to Bar</router-link>
  </p>
  <!-- 路由出口 -->
  <!-- 路由匹配到的组件将渲染在这里 -->
  <router-view></router-view>
</div>
```
javascrpt

```js
// 0. 如果使用模块化机制编程，導入Vue和VueRouter，要调用 Vue.use(VueRouter)

// 1. 定义（路由）组件。
// 可以从其他文件 import 进来
const Foo = { template: '<div>foo</div>' }
const Bar = { template: '<div>bar</div>' }

// 2. 定义路由
// 每个路由应该映射一个组件。 其中"component" 可以是
// 通过 Vue.extend() 创建的组件构造器，
// 或者，只是一个组件配置对象。
// 我们晚点再讨论嵌套路由。
const routes = [
  { path: '/foo', component: Foo },
  { path: '/bar', component: Bar }
]

// 3. 创建 router 实例，然后传 `routes` 配置
// 你还可以传别的配置参数, 不过先这么简单着吧。
const router = new VueRouter({
  routes // （缩写）相当于 routes: routes
})

// 4. 创建和挂载根实例。
// 记得要通过 router 配置参数注入路由，
// 从而让整个应用都有路由功能
const app = new Vue({
  router
}).$mount('#app')

// 现在，应用已经启动了！
```


### 我的router配置

```js
import Vue from 'vue'
import VueRouter from 'vue-router'
import blog from './admin/blog.vue'
import setting from './admin/setting.vue'
import user from './admin/user.vue'
import test from './admin/test.vue'
import login from './admin/login.vue'
import index from './index.vue'


Vue.use(VueRouter);

// 1. 定义（路由）组件。
// 可以从其他文件 import 进来
 const routes = [
    { path: '', component: index,
      children: [
        {
          // 当 /user/:id/profile 匹配成功，
          // UserProfile 会被渲染在 User 的 <router-view> 中
          path: '/blog',
          name:'博客',
          component: blog
        },
        {
          // 当 /user/:id/posts 匹配成功
          // UserPosts 会被渲染在 User 的 <router-view> 中
          path: '/setting',
          name:'设置',
          component: setting
        },
        {
        	path:'/user',
        	name:'用户管理',
        	component:user
        },
        {
        	path:'/test',
        	name:'测试',
        	component:test
        }
      ]
    },{
    	path:'/login',
    	component:login,
    	meta: { requiresAuth: true }
    }
  ]


const router = new VueRouter({
  routes
})

// router.beforeEach((to, from, next) => {
//   if (to.matched.some(record => record.meta.requiresAuth)) {
//     // this route requires auth, check if logged in
//     // if not, redirect to login page.

//     alert(1111);

//     if (!auth.loggedIn()) {
//       next({
//         path: '/login',
//         query: { redirect: to.fullPath }
//       })
//     } else {
//       next()
//     }
//   } else {
//     next() // 确保一定要调用 next()
//   }
// })



export default router
```

### 一些注意点
* 页面跳转 router.push()

```js
// 字符串
router.push('home')

// 对象
router.push({ path: 'home' })

// 命名的路由
router.push({ name: 'user', params: { userId: 123 }})

// 带查询参数，变成 /register?plan=private
router.push({ path: 'register', query: { plan: 'private' }})
```

* 监听页面跳转    

```js
watch: {
  '$route' (to, from) {
    //somecode
  }
}
```

