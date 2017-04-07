---
title: 如何高效的配置macpro工作环境
date: 2017-04-07 14:13:46
tags:
---
　本文记录整个配置过程，供新入手 MacBook 和觉得 MacBook 比较难用的同学参考。

　　1. 硬件提升

　　笔记本电脑的特点是携带方便，缺点是屏幕太小，因此你首先需要再申请领用一个外接显示器，多一个屏幕会大大减少你切换应用程序的次数，显著提升你的工作效率，别忘了同时申请一个 Mini DP 转 VGA 的转接头用于连接显示器。为了配合多显示器，后面会推荐一个软件来管理多显示器窗口。

　　如果你资金宽裕，可以买个机械键盘和无线鼠标，进一步提升工作效率。

　　2. 系统设置

　　2. 1 将功能键(F1-F12) 设置为标准的功能键

　　MacBook 键盘最上面一排的功能键(F1-F12) 默认是系统亮度和声音之类的快捷设置，当 MacBook 作为你的娱乐电脑时，这样的默认设置是非常方便的，但是对于将 MacBook 作为工作电脑而且需要频繁使用功能键(F1-F12) 的人，最好将功能键(F1-F12) 的行为设置为标准的功能键。

　　首先打开System Preferences，点击Keyboard图标，勾选上Use all F1, F2, etc. keys as standard function keys。以后如果你要调节音量，就按住键盘左下角的fn键再按 F11 或者 F12。

211

　　图 2.1-1

　　2. 2 设置 Trackpad（触摸板）轻触为单击

　　当你首次使用 MacBook，是否会觉得触摸板一点都不顺滑？那是因为你需要做如下设置。

　　打开System Preferences，点击Trackpad图标，勾选Tap to click选项，现在手指轻轻一碰触摸板，就达到鼠标单击的顺滑效果。

　　2. 3 将 Dock 停靠在屏幕左边

　　为什么要将Dock停靠在屏幕左边？MacBook 的屏幕是一个长方形，如果你将Dock放在下面，那么屏幕的可用宽度就会减少，另外人眼阅读时的顺序是从左往右，因此Dock放在左边更适合将 MacBook 作为工作电脑的人。

　　打开System Preferences，点击Dock图标，

将图标的Size调到合适大小
关闭Magnification特效（即鼠标放到 Dock 上图标放大的效果，此效果干扰注意力）
在Position on screen一栏，选择Left
勾选Minimize window into application icon
231

　　图 2.3-1

　　2. 4 全键盘控制模式

　　全键盘控制模式是什么？ 举一个例子，如下图所示，我正在写一个文档，此文档还没有保存，也没有文件名，如果不不小心点了关闭按钮，将会弹出一个对话框：

241

　　图 2.4-1

　　当前，[Save]按钮处于默认激活状态，按回车将会弹出保存对话框。但是如果我不想保存呢？ 只能通过鼠标或者触摸板来移动光标后点击[Don't Save]来取消保存。那我能不能通过键盘控制光标激活[Don't Save]按钮呢？ 答案是肯定的，做一个简单设置就好。

　　如图，首先打开System Preferences，点击Keyboard图标，选择Shortcuts这个 Tab, 选中All controls

242

　　图 2.4-2

　　现在当我再次试图关闭一个未保存的文件时，新弹出的对话框如下，有了些许变化，在[Don't Save]按钮上多了一个蓝色的外框，当你按键盘上的tab键的时候，蓝色的外框会在 3 个按钮间切换。 假设现在蓝色的外框在[Don't Save]按钮上，你按下回车，却发现系统依然进入了保存文件对话框，为什么蓝色的外框不起作用呢？那是因为蓝色的外框选中的按钮是由空格键触发的，当你按下空格键，系统就会不保存文件直接退出。 这样当你不方便使用鼠标和触摸板的时候，可以更快速的和你的 MacBook 交互。

243

　　图 2.4-3

　　2. 5 快速锁定屏幕

　　如果你长时间离开电脑，最好锁定你的屏幕，以防止数据泄露。 那如何快速的锁定你的 MacBook 呢？ 答案是只需要一摸触摸板或者一甩鼠标就可以了。

打开System Preferences，点击Desktop & Screen Saver图标，选择Screen Saver这个 Tab，再点击Hot Corners...，在弹出的如下界面里面，右下角选择Put Display to Sleep，点击 OK 确定。251
图 2.5-1

再打开System Preferences，点击Security & Privacy图标，在GeneralTab 内，勾选Require password[immediately] after sleep or screen save begins。
252

　　图 2.5-2

　　现在当你离开电脑前时，记得一摸触摸板或者一甩鼠标将光标快速的移到屏幕的右下角，MacBook 将立刻进入Screen Saver模式并且需要密码才能进入桌面。

　　3. 系统常用快捷键

　　请点击这个文档，学习系统快捷键，适当使用快捷键将会提升你的工作效率。

　　4. 日常软件推荐

　　4. 1 中文输入法

　　系统自带的输入法不是很好用，推荐安装搜狗输入法或者 RIME 输入法。安装完成后，打开System Preferences，选择Keyboard，切换到Shortcuts这个 Tab 下，勾选Select the previous input source，并点击上述文字后面的空白处，设置快捷键为Ctrl+Space(即如图所示的^Space)。

411

　　图 4.1-1

　　4. 2 窗口管理软件 - SizeUp

你是否经常想让某个 Word 文档占满屏幕的左半部分，旺旺聊天占满屏幕的右半部分，从而一边对着文档一边和小伙伴聊需求？
终于搞好了外接显示器，你是否经常将某个窗口在笔记本和外接显示器屏幕之间直接来回拖动？
　　SizeUp 快速解决这样的需求，该软件可以永久免费试用，下载安装后打开 SizeUp，再打开旺旺，快捷键按下control+option+command + M，则旺旺就会立即进入全屏模式。

　　然而大部分情况下，你会看到如下这个提示，这是因为 SizeUp 需要你的授权才能控制窗口。

421

　　图 4.2-1

　　直接点击Open System Preferences或者打开System Preferences，点击Security & Privacy图标，在PrivacyTab 内，点击Accessibility，然后将 SizeUp 加到右边的列表里面。（提示：你可能需要先点击右下角的黄色锁，输入密码后才能编辑右边的列表。）

422

　　图 4.2-2

　　如果你此时接上了外接显示器，快捷键按下control+option + 方向键右键，则当前左边显示器激活的最前端窗口将被立即发送到右边的显示器。

　　下面列举一些 SizeUp 常用的快捷键，更多的快捷键和使用方式请查询其官方网站。

control+option+command + M ： 使当前窗口全屏
control+option+command + 方向键上键 ： 使当前窗口占用当前屏幕上半部分
control+option+command + 方向键下键 ： 使当前窗口占用当前屏幕下半部分
control+option+command + 方向键左键 ： 使当前窗口占用当前屏幕左半部分
control+option+command + 方向键右键 ： 使当前窗口占用当前屏幕右半部分
control+option + 方向键左键 ： 将当前窗口发送到左边显示器屏幕
control+option + 方向键右键 ： 将当前窗口发送到右边显示器屏幕
　　4. 3 查找文件和应用程序以及无限想象力 - Alfred

　　如果你曾经使用过 MacBook，你应该接触过 Spotlight，就是屏幕中间弹出一个长条输入框，你输入文件名或者应用程序名，Spotlight 将模糊查找到对应的候选项，按回车快速的打开你需要的文件或程序。

　　Alfred 的能力远远超过了 Spotlight, 你可以直接下载免费版安装使用，Alfred 另外还提供了更强大的工作流(Workflows)和剪切板(Clipboard)管理等高级功能，需要购买 Powerpack。对于日常的操作，免费版已经足够使用了。

　　因为 Alfred 可以完全取代 Spotlight，下面先删除 Spotlight 占用的快捷键command + 空格，以供 Alfred 将来使用。

　　打开System Preferences，选择Keyboard，切换到Shortcuts这个 Tab 下，点击 Spotlight，取消对应的 2 个快捷键设置。

431

　　图 4.3-1

　　打开 Alfred，在菜单栏点击 Alfred 图标，打开Preferences...

432

　　图 4.3-2

　　如下图所示，设置 Alfred 的快捷键为command + 空格

433

　　图 4.3-3

　　现在按下快捷键command + 空格，输入ali，则 Alfred 不区分大小写的将所有包含ali的应用程序，文档以及历史网址都列出来了，如下图所示，回车打开淘云盘，command+2打开本地一个 xmind 文件，你还可以移动键盘上下键或者光标来选择目标。

434

　　图 4.3-4

　　更多关于 Alfred 的使用方式和无限想象力，请参考官方网站或者网上现有的大量的教程。

　　下面简单演示一下剪切板管理和厂内查人工作流的使用。如下图所示，我使用快捷键打开剪切板管理器，列出来我最近复制过的文本片段，我可以快速的选取这些文本片段或者输入部分字符来查找。

435

　　图 4.3-5

　　当你安装了由@文通开发的厂内查人 workflow 后，激活 Alfred，输入r+ 空格，再输入某人的花名，就可以看到对方的简单信息。

按回车打开阿里内外对方信息页面
按ctrl+ 回车，直接打开对方旺旺进入聊天模式
436

　　图 4.3-6

　　4. 4 聪明又美丽的日历 -- Fantastical 2

　　打开 Fantastical 2的网站，你一定会被她漂亮的外表所吸引，最可贵的是 Fantastical 还很聪明，当你在日历里面新建一个提醒的时候，输入如下内容“HTML training at 7:30pm tomorrow alert 5 min”， 则 Fantastical 会自动将日期设置为明天，然后将开始时间设置为晚上 7 点半，并且提前 5 分钟提醒，是不是很聪明？

441

　　图 4.4-1

　　4. 5 来杯免费咖啡 -- Caffeine

　　今天下午给大老板和重要客户演示 PPT，你仿佛看到了升职加薪走上人生巅峰，当你打开 MacBook 接上投影仪，口若悬河的讲解，突然 MacBook 进入休眠模式了，画面太美了，我不敢想了。

　　你应该立刻安装这款免费的良心软件---Caffeine，设置开机启动，点一下状态栏的咖啡杯图标，当咖啡是满的时候，MacBook 将不会进入休眠模式，再点一下咖啡杯空了就正常休眠，我默认设置开机启动，咖啡杯保持满满的状态。

　　4. 6 快速切换和打开应用程序 -- Manico

　　MacBook 系统默认设置了一个快捷键来显示当前运行中的应用程序，同时按下tab + command，将看到如下图的样式：

461

　　图 4.6-1

　　如果你想要却换到 Firefox，需要再按一下tab，如果要切换到日历，需要按两下‘tab’，如果一次性打开 10 几个应用程序，你经常需要按十几下tab才能却换到想要的程序。

　　Manico 专为这个场景而设计，安装好后打开，默认快捷键是按住option，如图所示，此时按下数字7就能快速打开编号为7的地图。

462

　　图 4.6-2

　　另外，推荐设置 Manico 使用左手边的字母加数字做索引，方便仅仅用左手就能快速切换应用程序。在菜单栏点击 Manico 图标，打开Preferences...， 在AppearanceTab 里面，选择Uses left hand area和Use numeric and alphabet。

463

　　图 4.6-3

　　4. 7 随心所欲的复制粘贴以及无限想象 -- PopClip

日常工作中，你有多少次是从一个应用程序复制一段文本然后粘贴到另外一个地方？
有多少次是复制一个网址然后打开浏览器粘贴到地址栏然后回车打开？
有多少次是复制一个名词，然后打开浏览器找到搜索引擎来搜索？
　　这些重复的操作模式都是可以简化的，你唯一需要的就是 PopClip，当你选中一段文字（如下图，选中“当日收益”），PopClip 就会弹出来一个快捷操作栏，你可以复制，剪切或者粘贴，更为强大的是，PopClip 提供了很多免费的插件，例如使用指定的搜索引擎搜索选中的文字，或者选中英文单词做大小写转换等等。

471

图 4.7-1

　　需要注意的是，PopClip 需要你的授权才能弹出快捷状态栏，直接点击Open System Preferences或者打开System Preferences，点击Security & Privacy图标，在PrivacyTab 内，点击Accessibility，然后将 PopClip 加到右边的列表里面并且勾选前面的 checkbook。（提示：你可能需要先点击右下角的黄色锁，输入密码后才能编辑右边的列表。）

　　4. 8 增强资源管理器 -- XtraFinder

　　MacBook 自带的资源管理器(Finder)已经可以满足一般的需要，但是当你有大量文件维护操作后，你就需要一个更强大的 Finder。XtraFinder 完全集成到 Finder 里面，你根本感觉不出它是一个第三方的应用程序，同时还提供很多增强特性，比如：

像浏览器那样的标签页(Tab)
支持双操作面板(Panel)
增强的全局快捷键，例如新建文件(New File)等
多彩的侧边栏图标
快速在当前文件夹打开终端
快速在当前文件夹新建文件
481

　　图 4.8-1

　　4. 9 随心所欲的全键盘控制 - Shortcat

　　在系统设置里面，我介绍了全键盘控制模式，但是此模式只能做简单的按钮控制，无法达到随心所欲的控制。下面介绍一款比较 geek 的软件，Shortcat 帮助你完全使用键盘来控制系统，供有键盘强迫症的同学使用。

491

　　图 4.9-1

　　4. 10 来杯鸡尾酒 -- Bartender

　　如果你看到这里，相信你已经被我推(hu)荐(you)的安装了一排软件，你的系统状态栏已经人满为患，有时候会因为当前激活的应用程序的菜单比较多挡住你要点击的状态栏图标，这个时候你需要一个酒保来帮你调理一下状态栏，Bartender 将是我推荐的最后一个日常使用的 App，你可以自定义隐藏某些不常用的状态栏图标，特别适合处女座强迫症。

4101

　　图 4.10-1

　　5. 开发环境配置

　　终于到了开发环境配置阶段，在配置开发环境前，建议先将 OS X 系统升级到最新版，同时去 Mac App Store 下载最新版的 Xcode，然后使用下面的命令安装 Xcode command line tools，这将为你安装很多终端下面常用的命令，将来很可能会使用到：

xcode-select --install
　　5. 1 命令行终端 Terminal

　　在用户界面没有发明前，终端 Terminal 曾经是计算机的唯一交互方式，就算到了今天，很多服务器仍然只提供终端登陆来操作，作为开发测试运维相关人员，在日常工作中合理使用终端将大大提高工作效率。

　　5. 1.1 替换系统默认 Shell -- Oh My ZSH!

　　Bash 作为大多数系统默认安装的 Shell，大家都多少有所接触，Zsh 和 Bash 类似都是一个 Shell，但是 Zsh 更注重用户体验和与人的交互，OS X 默认也安装好了 Zsh，然而你想自己从头开始配置一个顺手的 Zsh 是比较浪费时间的，有人已经帮我们配置好了，这个流行的 Zsh 配置叫---Oh My ZSH!，直观的效果如下图所示，代码开源在 github。

5111

　　图 5.1.1-1

切换默认 Shell 到 Zsh
　　Mac OS X 默认已经安装好了 Zsh，你可以打开终端，输入zsh --version来确认，如果没有安装，请参考这个文档。

　　打开终端输入下面的命令，切换默认 Shell 为 Zsh：

chsh -s /bin/zsh
　　关闭终端重新打开后，你将默认使用 zsh 作为终端 Shell。然而你会发现，终端并没有变得多酷炫，接着往下走，安装 Oh My ZSH!

安装 Oh My ZSH!
　　打开终端输入下面的命令：

sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
　　耐心等待一会儿，然后你就会发现你的终端变成了彩色的了。

5112

　　图 5.1.1-2

　　你可以修改终端的 Profile，选择深色背景 profile，这样就比较炫酷了。如果你对默认的Oh My ZSH的配色不满意，请参考这里找到你喜欢的配色。

　　5. 1.2 替换系统默认终端 -- iTerm 2

　　如果你经常使用终端，那么推荐你使用 iTerm 2来替代系统自带的终端。关于 iTerm 2 的特性，请看这里。

　　这里我只介绍一个小技巧，我想设置一个快捷键假设为 F12，在任意场合，我按一下快捷键 F12 就弹出终端，输入一些命令执行后，再按一下 F12 终端就自动隐藏，这对经常使用终端的人，例如经常 ssh 连接服务器的人来说实在太方便了。

　　设置过程如下：

系统已经默认将 F12 分配给Show Dashboard，需要先取消这个设置。
　　打开System Preferences，选择Keyboard，切换到Shortcuts这个 Tab 下，点击Mission Control，取消对应 F12 的快捷键。

5121

　　图 5.1.2-1

打开 iTerm 的Preferences...， 在ProfilesTab 里面，点击下面的[+]添加一个新的 profile，为什么要新建一个 profile？答案是为了定制将来弹出的终端样式和大小等等参数。新的 profile 假设命名为 guake，(注：guake 这个名称是为了向 Linux 下的 Guake 终端致敬)，你可以自己任意起个名称，下面会用到。
5122

　　图 5.1.2-2

　　再切换到WindowTab 下，将Style，Screen和Space这 3 个值设置和下图一样。

5123

　　图 5.1.2-3

　　再切换到KeysTab 下，设置如下图所示的HotkeyF12。

5124

　　图 5.1.2-4

　　现在你按下 F12，就立即得到一个占满全屏的黑色命令行终端，再按一下 F12 隐藏终端，非常的方便。

　　5. 2 终端下的命令管理 -- Homebrew

　　Mac App Store 你一定非常熟悉了，它可以帮你下载和安装大部分常见的软件。

　　在终端下，我们也需要一个 App Store 一样的管理程序，当你需要安装某个终端下的新命令的时候，这个程序可以帮助我们自动下载该命令以及相关的依赖，甚至在下载以后做必要的编译和环境设置。

　　Homebrew 就是这样一款终端下的命令程序包管理器，安装非常简单，复制如下命令在终端下运行，按回车并输入密码后等待安装成功：

ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
　　下面是安装截图：

521

图 5.2-1

　　curl 和 wget 是命令行下面常用的命令，其中 curl 已经默认安装在 OS X 中了，但是 wget 没有默认安装，下面演示如何使用 Homebrew 来安装 wget。

brew install wget
　　下面是运行截图：

522

　　图 5.2-2

　　5. 3 终端下管理非终端软件 -- Homebrew Cask

　　因为 Apple 不允许第三方的浏览器进入 Mac App Store，如果你想要安装 Google Chrome，只能去 Google 网站下载后运行安装文件。这一类 App Store 没有的非终端下的软件能不能享受 Homebrew 一样的命令行安装的便捷性呢？

　　Homebrew Cask 就是这样一款终端下的程序管理器，它扩展了 Homebrew，作为 Mac App Store 的有益补充，方便你快速维护日常软件的安装升级和卸载，复制如下命令在终端下运行，按回车后等待安装成功：

brew install caskroom/cask/brew-cask
　　下面是运行截图：

531

图 5.3-1

　　那如何使用 Homebrew Cask 来安装 Google Chrome 呢？ 首先使用chrome作为关键字查找一下：

> brew cask search chrome ==> Partial matches chrome-devtools chrome-remote-desktop-host chromecast google-chrome
　　上面的命令运行后列出了 4 个候选项，很明显最后一个google-chrome就是我们要安装的，继续输入

> brew cask install google-chrome
　　下面只需要稍微等一会儿，最新版的 Google Chrome 就乖乖的安装在你的 MacBook 里面了。

　　5. 4 Java 开发环境搭建

　　5. 4.1 安装 Java 和 Maven

　　现在 OS X 没有默认安装 JDK，如果你在终端输入java，系统会引导你到 Oracle 网站去下载，然后自己点击下载文件来安装，这个过程一点都不酷，而且不能自动化。现在你有了 Homebrew Cask，只要输入如下命令，Java 就可以自动安装好啦。

brew cask install java
　　现在最近版本的 JDK 是 1.8，Homebrew 默认安装最新版软件，如果你要安装非最新版的 JDK，那么去 Oracle 网站下载吧，Homebrew 的多版本支持不是很好用。

　　同样的，输入如下命令来安装 Maven 最新版。

brew install maven
　　在开发中，你很可能会碰到这个错误java.security.InvalidKeyException: Illegal key size or default parameters，那是因为美国对出口软件加密算法长度的限制，你需要去如下链接下载补丁包：

JCE Unlimited Policy for JDK 6
JCE Unlimited Policy for JDK 7
JCE Unlimited Policy for JDK 8
　　补丁替换路径为${java.home}/jre/lib/security/，大约如下所示：

/Library/Java/JavaVirtualMachines/jdk1.8.0_51.jdk/Contents/Home/jre/lib/security
　　5. 4.2 安装版本控制软件 -- SmartGit & SmartSVN

　　如果代码就是生命，版本控制系统就是时光机。Git 和 Subversion 分别是现在最流行的 2 个版本控制系统，SmartGit 和 SmartSVN 分别是他们的一个第三方客户端，当然他们有很多第三方客户端，我觉得 SmartGit 和 SmartSVN 是最好用的。

　　5. 4.3 安装和配置 IDE -- IntelliJ IDEA

　　IntelliJ IDEA 作为最智能的 Java IDE，推荐所有 Java 开发人员使用，你可以在这里下载安装文件，或者使用如下的 Homebrew Cask 命令来下载安装：

brew cask install intellij-idea
　　打开 IDEA，推荐选择Darcula主题，快捷键映射选择I've never used IDEA, 一路确认下去进入主界面。

　　推荐使用版本控制客户端(SmartGit & SmartSVN)下载好源代码后，再使用 IDEA 导入源代码，原因是如果用 IDEA 来 checkout 源代码，一边 checkout 一边分析代码，对于有多个模块的 Maven 项目，IDEA 动态检测 Spring 框架的配置文件可能会得不到及时而完整的依赖分析。

5421

　　图 5.4.2-1

　　我们假设项目是基于 Maven 的，如下图，选择Maven：

5422

　　图 5.4.2-2

　　一路点击[Next]进入主界面，IDEA 会帮我们自动检测到依赖的框架，如图 IDEA 发现我们使用了 OSGI 和 Spring 框架，点击[Configure]，然后去除 OSGI 依赖，因为 SOFA 项目不是完全实现 OSGI 规范的，勾选 Spring 配置文件。

5423

　　图 5.4.2-3

　　IDEA 会在你首次导入一个项目的时候建立索引，耐心等待索引建立完成，之后的查找就会非常快速。

　　6. 工具的意义

　　工欲善其事，必先利其器，工具永远都是用来解决问题的，没必要为了工具而工具，一切工具都是为了能快速准确的完成工作和学习任务而服务。