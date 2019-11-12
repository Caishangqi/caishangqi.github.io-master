---
layout: post
title: "SecondTech 客户端配置文件修改总结"
date: 2019-06-28
description: "配置文件修改"
tag: 教程
---   

### **介绍**
调整客户端一直都是服务器重要的一部分，同时也要确保客户端拥有高度配置性 ***即*** 玩家可以修改相

关配置文件影响游戏体验

### **可供修改列表**
**原版修复 VanillaFix**
>* [下载地址](http://www.mcbbs.net/thread-792493-1-1.html) 来源:国内

**基本修改**

屏蔽非`灾难性`错误

VanillaFix不再会让游戏应为错误崩溃,相反它会生成错误报告

**如图:** ![](/images/posts/markdown/image7.PNG)

一连串的报错不仅会遮挡游戏画面，并且会降低游戏FPS,因此很有必要将报错信息**去除**或者**缩短**

>* **步骤一 打开配置文件**

打开模组对应的配置文件 路径在 `\.minecraft\config\vanillafix.cfg`中,如果你是整合包安装，路径在 `\.minecraft\versions\版本号\config\vanillafix.cfg` 中

>* **步骤二  了解可以自定义的变量**

配置文件内容总览:

```
crashes {
    B:disableReturnToMainMenu=false
    I:errorNotificationDuration=30000
    S:hasteURL=https://paste.dimdev.org
    B:replaceErrorNotifications=false

    # Valid values:
    # LOG
    # NOTIFICATION
    # WARNING_SCREEN
    # CRASH
    S:scheduledTaskproblemAction=NOTIFICATION
}


fixes {
    B:bugFixes=true
    B:crashFixes=true
    B:modSupport=true
    B:profiler=true
    B:textureFixes=true
}

```
>* **步骤三  修改相关变量的配置**


`scheduledTaskproblemAction`是提示形式,若想取消屏幕显示可以直接修改为 `S:scheduledTaskproblemAction=LOG`

`I:errorNotificationDuration`是错误信息显示时间，若想要更短的显示时间即可修改此选项为 `I:errorNotificationDuration=10000`

`B:replaceErrorNotifications`是错误信息重复选项，若设置`true`，则不会有重复错误信息

`B:disableReturnToMainMenu`是出错返回菜单选项，建议设置为`false`防止数据丢失

>* **添加优化模组 错误排查推荐设置**

`scheduledTaskproblemAction`设置为`S:scheduledTaskproblemAction=NOTIFICATION`

`I:errorNotificationDuration`设置为 `I:errorNotificationDuration=20000`

`B:replaceErrorNotifications`设置为 `B:replaceErrorNotifications=false`

**仔细阅读网站报错信息去分析模组间的冲突,它可能会显示在网页报错信息里而不是客户端中**
