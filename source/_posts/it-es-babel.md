---
title: 使用babel编译es6语法
date: 2018-02-03 18:05:42
tags: node
---


先安装babel-cli工具

```bash
npm install babel-cli -g
```

### 使用


```bash
# 转码结果输出到标准输出
$ babel example.js

# 转码结果写入一个文件
# --out-file 或 -o 参数指定输出文件
$ babel example.js --out-file compiled.js
# 或者
$ babel example.js -o compiled.js

# 整个目录转码
# --out-dir 或 -d 参数指定输出目录
$ babel src --out-dir lib
# 或者
$ babel src -d lib

# -s 参数生成source map文件
$ babel src -d lib -s
```
<!-- more -->
安装es5的编码规则


```
$ npm install --save-dev babel-preset-es2015

```

创建.babelrc 配置文件 


```json
{
  "presets": ["es2015"],
  "plugins": []
}
```



### 参考
http://es6.ruanyifeng.com/#docs/intro


