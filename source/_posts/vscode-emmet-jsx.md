---
title: vscode react Emmet 补全
date: 2018-04-04 10:13:30
tags: react
---

>  在开发react项目中，我们使用的都是js'x的语法 vscode默认emmet不支持jsx补全 

在设置中添加一下代码片段就行了 

```js
"emmet.includeLanguages": {
    "javascript": "javascriptreact"
},
"emmet.triggerExpansionOnTab": true
```

###  参考资料

https://segmentfault.com/q/1010000005780723