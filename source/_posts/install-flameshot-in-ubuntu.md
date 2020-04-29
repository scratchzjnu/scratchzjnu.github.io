---
title: 在Ubuntu中安装FlameShot
date: 2020-04-25 21:14:23
tags: [linux] 
---

FlameShot是Linux下一个非常不错的截屏软件，安装与使用也比较简单，功能也比较全。

#### 安装FlameShot
软件已经收录到Ubuntu的应用仓库了，所以安装很简单。
```
sudo apt install flameshot
```
<!--More -->


#### 使用FlameShot
安装后软件的位置在`/usr/bin/flameshot` ，运行的参数是：`/usr/bin/flameshot guibin/flameshot gui`。可以为它在快速启动面板中创建一个快捷图标。

另外，也可以创建一个系统快捷键，在Lubuntu启动菜单中是在”系统工具“/”setup hotkeys”中。
在“Program”中添加一个新的项目，执行的命令是：`/usr/bin/flameshot gui`, 可以设置一个自己习惯的快捷键，例如：`CTRL+ALT+A` （微信Windows客户端中也是这个吧？）

另外，如果使用的是Lubuntu 18.10以后版本（LXQT桌面），可以直接在启动菜单中将这个图司法往快捷启动栏拖动即可增加快捷启动图标，作为一个高频应用，这样也很方便