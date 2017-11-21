---
title: vue文件中使用scss解决报错问题
date: 2017-06-26 15:53:14
tags: [vue,webpack]
---

vue-cli手脚架中没有安装sass-loader
需要自行安装 在vue文件中使用 scss 写css会报错 需要到webpack中配置

```json
{
        test: /\.vue$/,
        loader: 'vue-loader',
        options: {
          loaders: {
            'scss': 'style-loader!css-loader!sass-loader'
          }
        }
      }
```
如果需要在vue文件style标签使用scss的话，需要声明一下：

```html
<style rel="stylesheet/scss" lang="scss">
```


