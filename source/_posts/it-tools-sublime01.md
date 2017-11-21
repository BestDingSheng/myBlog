---
title: sublime个性化设置
date: 2017-11-01 14:46:52
tags: 编辑器
---

推荐使用主题 Material Theme  http://equinsuocha.io/material-theme/  

安装好后在sublime设置下

推荐字体 Comic Sans MS

```json
{
	"color_scheme": "Packages/Material Theme/schemes/Material-Theme.tmTheme",
	"font_face": "Comic Sans MS",
	"font_size": 16,
	"ignored_packages":
	[
		"Vintage"
	],
	"theme": "Material-Theme.sublime-theme"
}

```

<!--more-->

sublime自带的格式化 在快捷键里面设置下

```json
[{
    "keys": ["ctrl+z"],
    "command": "reindent",
    "args": {
        "single_line": false
    }
}]
```

