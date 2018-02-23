---
title: 下一代打包工具parcel
date: 2017-12-28 16:08:47
tags: parcel
---

官网 https://parceljs.org/



vue项目parcel配置

```json

{
  "name": "vue-parcel",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT",
  "scripts": {
    "dev": "parcel index.html",
    "build": "parcel build index.html --public-url /"
  },
  "devDependencies": {
    "babel-preset-env": "^1.6.1",
    "less": "^2.7.3",
    "node-sass": "^4.7.2",
    "parcel-bundler": "^1.2.0",
    "parcel-plugin-vue": "^1.0.1"
  },
  "dependencies": {
    "echarts": "^3.8.5",
    "vue-router": "^3.0.1"
  }
}

```


