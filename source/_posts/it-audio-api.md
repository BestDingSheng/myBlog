---
title: HTML5<Audio标签API整理>
date: 2017-08-01 10:21:52
tags: html
---

### 只读属性
duration ---获取媒体文件的播放时长，以s为单位，如果无法获取则为NaN，当触发canplay事件后就可以获取当前总长度
startTime---返回起始播放时间，一般是0.0,除非是缓冲过的媒体文件，并一部分内容已经不再缓冲区(此属性好像已经不可用)
paused-----判断是否已经暂停，返回true/false
ended-----判断是否已经播放完毕，返回true/false
error----在发生了错误后，返回错误代码
currentSrc --以字符串的形式发挥正在播放或已经加载的文件，对应浏览器在source元素中选择的文件
buffered---获取当前缓冲区大小，返回TimeRanges对象，点击更多参考

<!--more-->

### 可控制属性
src----指定音频的文件位置
autoplay---是否自动播放
preload----是否预加载
loop------是否循环播放
controls----显示或隐藏用户控制界面
autobuffer---媒体文件播放前是否进行缓冲加载，如果设置了autoplay，则忽略此特性(此属性好像已经不可用)
muted------设置是否静音
volume ----在0.0到1.0间的音量值，或查询当前音量值
currentTime--以s为单位返回从开始播放到目前所花的时间，也可设置currentTime的值来跳转到特定位置

### 方法
load() ---加载音频、视频软件
paly() ---播放
pause()---暂停
canPlayType(obj) ----测试饭后指定指定的Mime类型的文件

### 事件
loadstart ---客户端开始请求数据
progress----正在播放的时候不停触发，如果暂停不会触发，触发的时间间隔比较大
play------play()和autopaly播放时，类似事件onplaying
pause-----pause()方法触发时
ended-----当结束播放时
timeupdate----当前播放时间发生改变的时候，播放中常用的时间处理，如果暂停不会触发，触发的时间间隔比较小
canplaythrough---歌曲已经载入完成
canplay -----缓冲至可播放状态，类似事件onloadedmetadata
onloadedmetadata----当元数据（比如分辨率和时长）被加载时运行的脚本

###  更多属性

audioTracks----返回表示可用音频滚到的AudioTrackList对象。
controller---返回表示音频大年媒体控制器的MediaController对象。
crossOrigin---设置或返回音频的CORS设置
defaultMuted---设置或返回音频默认是否静音
defaultPlaybackRate---设置或返回音频的默认播放速度
mediaGroup---设置或返回音频叔叔的美肌组合的名称
networkState---返回音频的当前网络状态
playbackRate---设置或返回音频的播放速度。
seekable---返回标识音频可寻址不烦的TimeRanges对象
seeking---返回用户当前收正在音频中进行查找。
textTracks---返回标识文本滚到的TextTrackList对象

### 更多方法

load()----重新加载音频元素
getStartDate()----返回新的Date对象，表示当前时间线偏移量。
fastSeek()---在音频播放器中指定播放时间。
addTextTrack()----想音频添加新的文本轨道。
更多参考：http://caibaojian.com/html5-audio.html

