---
title: postcss && cssnext
date: 2018-03-14 09:02:55
tags: css
---

> postcss和cssnext是什么关系呢 就相当是babel和es6的关系 nextcss是下一代的css语法很增了很多新的特性 但是大多浏览器目前还不支持，postcss能把cssnext编译成目前浏览器能兼容的css
> 


postcss官网 http://postcss.org/

cssnext官网 http://cssnext.io/playground/

postcss对现在主流的工程化工具都有对应的插件

<!-- more -->


### webpack postcss 常用插件

postcss.config.js

```
module.exports={
	plugins:[	
	require('postcss-custom-selectors'),  // 解析自定义选择器
	require('autoprefixer')({browsers: ["ios >= 7", "android >= 4.0"]}), // 添加浏览器内核
	require('postcss-apply')(), // 解析apply
	require('postcss-custom-media'), // 解析media变量
	require('postcss-image-set-polyfill'), // 转行分辨率适配方案
	require('postcss-preset-env'), // next语法解析
	]
}
```

webpack.config.js


```
  {
      test: /\.css$/,
      use: ExtractTextPlugin.extract({
          fallback: "style-loader",
          use: ["css-loader","postcss-loader"]
      })
  }
```



### 学习资料

https://div.io/topic/1575





