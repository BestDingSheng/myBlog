---
title: 命令开发笔记
date: 2018-01-17 15:30:11
tags: node
---

> 昨天无意间看到别人的博客写开发自己的cli工具，于是我就认真的看了一遍 源码只有十来行代码 看着挺简单 于是我就是自己尝试开发一个属于自己的cli工具




### 开发步骤

*  mkdir cmdTest && cd cmdTest
*  npm init -y
*  package.json 添加bin
     <!-- more -->    
```   
"bin": {
    "ding-cli": "./bin/index.js"
 }   
```

* ding-cli 就是我的命令
* 我们现在到bin/index.js 编辑这个页面
* 下面是我的index文件

```bash

#! /usr/bin/env node 

console.log('hello world');
```

*  npm link 关联到全局 然后就能在命令行里输入 ding-cli 命令行就能出现hello world了


如果想要让别人也能用把这个模块上传到 npm 上面去就行了

### 参考资料 

* https://www.jianshu.com/p/5d0eef9724e0
* https://sfantasy.gitbooks.io/node-in-action/content/zh/cli/output.html 
* https://github.com/SFantasy/node-translator
* https://www.cnblogs.com/zhaowinter/p/5945067.html
* https://www.jianshu.com/p/2cae952250d1
* https://aotu.io/notes/2016/08/09/command-line-development/index.html





