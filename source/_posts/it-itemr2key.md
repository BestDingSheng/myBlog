---
title: Mac iterm2常用快捷键
date: 2017-04-08 15:50:37
tags: [itemr2,mac]
---



> 不会命令行的程序员不会好程序员不是好前端
码代码的时候听音乐更有激情哟 
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="//music.163.com/outchain/player?type=2&id=33937655&auto=0&height=66"></iframe>

早上上班的时候看到地铁站 速度与激情的广告 
电影中最爱的一个系列 满满的情怀 来首 see you again 回顾下两年前的速7
![](http://oo0pbw6u4.bkt.clouddn.com/IMG_1732.jpg)

<!--more-->

mac下的命令行工具首推itemr2

为什么推荐itemr2可以看这片文章 [快来戳我](https://www.zhihu.com/question/27447370)

下面是itemr2常用的快捷键，会了快捷键妈妈再也不用担心我不会装逼了


### 标签
* 新建标签：command + t

* 关闭标签：command + w

* 切换标签：command + 数字 command + 左右方向键

* 切换全屏：command + enter

* 查找：command + f


### 分屏

* 垂直分屏：command + d

* 水平分屏：command + shift + d

* 切换屏幕：command + option + 方向键 command + [ 或 command + ]

* 查看历史命令：command + ;

* 查看剪贴板历史：command + shift + h

### 其他

* 清除当前行：ctrl + u

* 到行首：ctrl + a

* 到行尾：ctrl + e

* 前进后退：ctrl + f/b (相当于左右方向键)

* 上一条命令：ctrl + p

* 搜索命令历史：ctrl + r

* 删除当前光标的字符：ctrl + d

* 删除光标之前的字符：ctrl + h

* 删除光标之前的单词：ctrl + w

* 删除到文本末尾：ctrl + k

* 交换光标处文本：ctrl + t

* 清屏1：command + r

* 清屏2：ctrl + l

### 自带有哪些很实用的功能/快捷键

* ⌘ + 数字在各 tab 标签直接来回切换

* 选择即复制 + 鼠标中键粘贴，这个很实用

* ⌘ + f 所查找的内容会被自动复制

* ⌘ + d 横着分屏 / ⌘ + shift + d 竖着分屏

* ⌘ + r = clear，而且只是换到新一屏，不会想 clear 一样创建一个空屏

* ctrl + u 清空当前行，无论光标在什么位置

* 输入开头命令后 按 ⌘ + ; 会自动列出输入过的命令

* ⌘ + shift + h 会列出剪切板历史

* 可以在 Preferences > keys 设置全局快捷键调出 iterm，这个也可以用过 Alfred 实现


### 我常用的一些快捷键

* ⌘ + 1 / 2 左右 tab 之间来回切换，这个在 前面 已经介绍过了

* ⌘← / ⌘→ 到一行命令最左边/最右边 ，这个功能同 C+a / C+e

* ⌥← / ⌥→ 按单词前移/后移，相当与 C+f / C+b，其实这个功能在Iterm中已经预定义好了，⌥f / ⌥b，看个人习惯了

### 设置方法如下

* 当然除了这些可以自定义的也不能忘了 Linux 下那些好用的组合

* C+a / C+e 这个几乎在哪都可以使用

* C+p / !! 上一条命令

* C+k 从光标处删至命令行尾 (本来 C+u 是删至命令行首，但iterm中是删掉整行)

* C+w A+d 从光标处删至字首/尾

* C+h C+d 删掉光标前后的自负

* C+y 粘贴至光标后

* C+r 搜索命令历史，这个较常用

### 选择喜欢的配色方案。

* 在Preferences->Profiles->Colors的load presets可以选择某个配色方案。也可以自己下载。在网站http://iterm2colorschemes.com/ ，几乎可以找到所有可用的配色方案。

### 选中即复制

iterm2有2种好用的选中即复制模式。

* 一种是用鼠标，在iterm2中，选中某个路径或者某个词汇，那么，iterm2就自动复制了。

* 另一种是无鼠标模式，command+f,弹出iterm2的查找模式，输入要查找并复制的内容的前几个字母，确认找到的是自己的内容之后，输入tab，查找窗口将自动变化内容，并将其复制。如果输入的是shift+tab，则自动将查找内容的左边选中并复制。


### 路径重复

* 在新Tab中自动使用前一Tab路径，如此设置：
![](http://img.blog.csdn.net/20160527095312397)


### 系统热键

* 如下图，设置好系统热线之后，将在正常的浏览器或者编辑器等窗口的上面，以半透明窗口形式直接调出iterm2 shell。
![](http://img.blog.csdn.net/20160527095435726)


### 自动完成

* 输入打头几个字母，然后输入command+; iterm2将自动列出之前输入过的类似命令。
![](http://img.blog.csdn.net/20160527095603804)


### 剪切历史

* 输入command+shift+h，iterm2将自动列出剪切板的历史记录。如果需要将剪切板的历史记录保存到磁盘，在Preferences > General > Save copy/paste history to disk.中设置。
![](http://img.blog.csdn.net/20160527095628398)


### 全屏切换

* command+enter进入与返回全屏模式

### Exposé所有Tab

* command+option+e,并且可以搜索
### 保存当前快照

* Window > Save Window Arrangement.
### 同样，恢复快照：

* Window > Restore Window Arrangement

 * 可以在Preferences > General > Open saved window arrangement.设置自动恢复快照


-------

<div  align=center>
    <center> 扫描二维码添加丁盛为你的好友</center ><center><font color=#f75000 size=>技术、户外、摄影、自驾 欢迎交流</font><center><img width='40%' align='center' src='/uploads/wechat-qcode.jpg
'>
</div>

