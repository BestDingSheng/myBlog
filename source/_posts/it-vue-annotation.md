---
title: vscode插件
date: 2017-08-17 10:46:54
tags: [编辑器]
---


> 好的开发工具能大大提升开发效率，目前我在用的是vscode 这里推荐些我目前常用的插件


1. Beautify 代码格式化工具
2. Spacgray VSCode 主题
3. Vetur vue代码高亮格式化插件
4. vue 提示vue语法

<!--more-->

下面是我的一些配置

```
// 将设置放入此文件中以覆盖默认设置
{
    "editor.fontSize": 12,
    "workbench.iconTheme": "vscode-great-icons",
    "workbench.colorTheme": "Spacegray Eighties Dark",
    "workbench.welcome.enabled": true,
    "extensions.ignoreRecommendations": false,
    "beautify.language": {
        "js": {
            "type": [
                "javascript",
                "json"
            ],
            "filename": [
                ".jshintrc",
                ".jsbeautify"
            ]
        },
        "css": [
            "css",
            "scss"
        ],
        "html": [
            "htm",
            "html",
            "vue"
        ]
    },
    "emmet.syntaxProfiles": {
        "vue":"html",
        "vue-html":"html"
    }
}
```

