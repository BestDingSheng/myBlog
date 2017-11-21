---
title: mac上最好用的svn客户端Cornerstone
date: 2017-04-13 16:37:52
tags: [mac]
---
[点击我下载Cornerstone破解版](http://xclient.info/s/cornerstone.html)
### 使用
标签：
前面几篇文章我介绍SVN服务器的安装，配置，实战。当然其中也加入了一些客户端测试的命令，使用命令当然是一个非常好的选择，但是对我们人类来说还是喜欢图形化界面的操作的。因此本文将介绍我喜欢的一款SVN客户端工具的使用。
<!--more-->
想要安装的Cornerstone的朋友，我有个坏消息是，如果你想使用它的正版软件，你是需要花费几十美金的，当然这里我带给您的永远都是有价值的好的信息，那就是在我们天朝使用软件还花钱真的是极品，我就奉献一下我在网上找到的一个比较好的破解版：http://pan.baidu.com/s/1o6F31zG
这个破解版本的Cornerstone软件安装方法我就不做介绍了，因为太容易。本文重点介绍一下它的使用方法。
当你打开软件时候会看到如下图所示界面：

![](https://ss0.baidu.com/6LVYsjip0QIZ8Aqbn9fN2DC/timg?pa&quality=100&size=w4096&sec=1492056426&di=0294f63bef43eef6328b8d99e4af51d4&ref=http%3A%2F%2Fwww%2Emamicode%2Ecom%2Finfo%2Ddetail%2D1123118%2Ehtml&src=http%3A%2F%2Fimages2015%2Ecnblogs%2Ecom%2Fblog%2F119556%2F201511%2F119556%2D20151121002400374%2D2081596969%2Epng)
现在是空空如也，因此我们应该做点什么，让它发挥作用。界面还是非常的直观和有引导性的，我直接按灰色区域的“Add repository” 
![](https://ss0.baidu.com/6LVYsjip0QIZ8Aqbn9fN2DC/timg?pa&quality=100&size=w4096&sec=1492056426&di=58381f52b11ca4eb47d1caaf11bd3414&ref=http%3A%2F%2Fwww%2Emamicode%2Ecom%2Finfo%2Ddetail%2D1123118%2Ehtml&src=http%3A%2F%2Fimages2015%2Ecnblogs%2Ecom%2Fblog%2F119556%2F201511%2F119556%2D20151121002418765%2D1837537103%2Epng)
完成点击之后会弹出配置界面，一般我们会使用第四个选项卡”SVN Server”.如图
图中我对SVN服务器做了访问的svn服务器配置,配置介绍如下： 
![](https://ss0.baidu.com/6LVYsjip0QIZ8Aqbn9fN2DC/timg?pa&quality=100&size=w4096&sec=1492056426&di=1b68139cf0ebf06c72eca967a63557fb&ref=http%3A%2F%2Fwww%2Emamicode%2Ecom%2Finfo%2Ddetail%2D1123118%2Ehtml&src=http%3A%2F%2Fimages2015%2Ecnblogs%2Ecom%2Fblog%2F119556%2F201511%2F119556%2D20151121002453108%2D1013518228%2Epng)
tunnel：访问通道，默认不用修改
Server：我的svn服务器在本地，所以Server填写了localhost
Port:设置端口号，我在服务器上没有配置访问端口号，所以port留空
Repository Path:这个是服务器仓库的目录位置，我这里填写了company，这是因为我在SVN服务的根路径下添加了company仓库。
Nickname:显示名。这个可以随便填写，建议为仓库和用户名的组合。
如果您的配置正确应该会添加成功的，如果错误，请检查服务器是否开启和你配置是否正确等。 下图是我们添加仓库成功后的效果图：
![](https://ss0.baidu.com/6LVYsjip0QIZ8Aqbn9fN2DC/timg?pa&quality=100&size=w4096&sec=1492056426&di=38cbd86f4e745649763ed6590ca5f83a&ref=http%3A%2F%2Fwww%2Emamicode%2Ecom%2Finfo%2Ddetail%2D1123118%2Ehtml&src=http%3A%2F%2Fimages2015%2Ecnblogs%2Ecom%2Fblog%2F119556%2F201511%2F119556%2D20151121002744733%2D689360189%2Epng)
从图中可以看到我昨天写的《SVN服务器配置实战》中的目录结构了。
现在我们来试试CorenerStone是如何代替我们的命令行的.下图介绍各个功能模块的作用： 
![](https://ss0.baidu.com/6LVYsjip0QIZ8Aqbn9fN2DC/timg?pa&quality=100&size=w4096&sec=1492056426&di=aa7daa9418300b710518f01477a49b6e&ref=http%3A%2F%2Fwww%2Emamicode%2Ecom%2Finfo%2Ddetail%2D1123118%2Ehtml&src=http%3A%2F%2Fimages2015%2Ecnblogs%2Ecom%2Fblog%2F119556%2F201511%2F119556%2D20151121002820874%2D871984781%2Epng)
四、使用简介
1.上传项目到repository
可以直接拖动到repository的子文件夹中，或是选择软件上方的Import按钮上传，会弹出选项填写所在位置及名称，然后选择Import即可
2.下载项目
下载分为两种：Export和Check Out，区别在于，Export后的项目不会与repository中的源文件相关联，是一个独立的版本，而Check Out下来的文件会创建一个working copy，参见步骤三的第一幅图，此文件与库中源文件相关联，当有新版本（他人修改）或是本地修改（自己修改）时，working copy会显示修改数量，白色数量为他人修改数量，灰色数量为本人修改数量
所以如果你是项目中的开发人员，可以选择check out，如果只是下载查看，不希望自己的修改影响到整个项目，最好是选择Export
3.版本管理
每一次提交会创建一个新版本，在repository中会保存所有历史版本，如下图（可通过修改人及提交信息进行检索版本），所以用svn开发可以很好的控制项目出现不可解决及未知bug时代码的修复问题：
svn方便了多人开发同一项目的代码合并问题，但是也有一些事项需要注意：
①先更新后提交
在看到有新版本（即同伴已经提交代码时），先更新代码，直至working copy不再显示白色圈，然后运行代码确定可运行且功能无误之后再commit自己的代码，否则，会造成项目中出现多处冲突或bug，且很难排查原因
②完成独立功能后再提交，且务必填写提交信息
每完成一个独立的功能，或解决一个bug之后再提交代码，不要连续多次重复提交，造成版本过多过杂，且提交时务必填写提交信息，交代本次完成了什么功能，方便上图中可以进行message的搜索来查看历史版本
③冲突文件
原则上同一组开发人员最好不要在同一文件中进行操作，但有时候必须去其他文件中进行操作，或者是误操作，如果同时多人在同一文件的同一位置修改代码，后提交的人会出现版本冲突文件，一般会有三个同样名称不同后缀的文件
.mine文件：本人所做修改
两个.r0XX文件：XX为数字，数字较小的为更改前的文件，较大的为更改后的文件，在文件中会有<<<< mine .r0XX  >>>>>等字样包含起来的代码，即冲突的地方，此时请和组内同事讨论或自己删除某部分修改文件后进行调试，修复文件
针对ios项目：出现某个工程或文件打不开的情况，如果为.project文件无法打开，则选择显示包内容->用文稿打开project.pbxproj文件->搜索.mine，将.mine部分前后<<<< >>>>包含起来的代码删除，工程就可以打开了，如果build时出现某个xib文件打不开的错误，则选中，用文稿打开，跟上文同样操作即可解决无法build的问题
④新添加文件
提交时新增加的文件显示为问号状态的，请选中右击后 选择Add to Working Copy之后再commit


-------

<div  align=center>
    <center> 扫描二维码添加丁盛为你的好友</center ><center><font color=#f75000 size=>技术、户外、摄影、自驾 欢迎交流</font><center><img width='40%' align='center' src='/uploads/wechat-qcode.jpg
'>
</div>

