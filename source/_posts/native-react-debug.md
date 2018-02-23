---
title: RN debug学习笔记
date: 2018-02-05 10:26:20
tags: RN
---

最近在学习RN这几记录下学习中DEBUG的一些笔记

1.开发者菜单的Reload选项
Reload代表重新加载程序的js代码,意味着程序会重新运行,并且你修改过后的js代码会更新,并运行.也就是开发者菜单中的第一项.每次修改代码,需要重新运行,只需调出开发者菜单,选中Reload即可.

2.开发者菜单中的Enable Live Reload选项
这个功能相当于Reload自动执行的选项,在开发者菜单的第二个选项.这个选项选中后,开发会变得更方便.当你修改代码后,便会自动执行.那么如何触发呢?毕竟不是你修改一行就加载一行,那样也不太正常啊.在subline中,只需按下crlt+s 这个保存的快捷键,即可调出live reload功能.

3.开发者菜单中的Enable Hot Reloading选项
这个功能相当于上面的live reload的加强版.也就是实时热修复,并直接达到当前所在的界面,保留当前的运行状态.类似android studio中的instant run,修改下界面后,直接显示修改后的ui效果.
注意: 这里的reload,live reload,hot reload都指的是js代码层面的调试,如果是android中或者ios中加入了图片资源,或者native代码有修改那就不行了,必须要重新编译才能看到效果.


### 参考
http://blog.csdn.net/aa671125/article/details/60874945

