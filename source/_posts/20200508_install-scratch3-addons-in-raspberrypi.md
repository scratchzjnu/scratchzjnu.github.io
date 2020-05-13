---
title: 树莓派中安装Scratch 3及GPIO插件
date: 2020-05-08 07:27:50
category: 创客与学科教学应用
tags: [raspbeery-pi, scratch]
---

#### 安装Scratch 3

首先要注意Scratch 3只支持2019年发布的Raspbian Buster及以后的版本。如果运行的系统版本不满足此条件，可以更新，也可以考虑使用Scratch 2。

如果在桌面环境可视化安装，可以在菜单的“属性”/“推荐软件”中，选择“Scratch3”，再点击“OK”。
如果要使用终端安装，可以使用以下命令：
```
sudo apt update
sudo apt install scratch3
```
<!--more-->

#### 添加GPIO插件
装好Scratch 3之后，点击树莓派图标/“编程”，然后找到“Scratch 3”图标即可启动Scratch 3。

单击左侧底部蓝色的图标，选择打开页面中的“Raspberry Pi GPIO”，此时在左侧组件列表中即可以找到GPIO的选项。

#### 其它信息

如果使用的是Scratch 2，在启动后先打开“More Blocks”面板，单击“Add an extension”，选择“Pi GPIO”。
