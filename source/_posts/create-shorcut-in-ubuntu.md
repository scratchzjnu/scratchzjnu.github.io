---
title: Ubuntu中创建桌面快捷方式
date: 2020-04-26 09:17:30
tags: [linux]
---

在Ubuntu系统中要创建程序的快捷方式，可以通过创建`.desktop`文件的方式来实现。这里以Sublime Text 3为例，先创建一个名为`sublime-text.desktop`的文件，内容如下：
```
[Desktop Entry]
Version=1.0
Type=Link
Name=Sublime Text 3
Comment=Launch Sublime Text 3 Editor
URL=/usr/bin/subl
Icon=/usr/share/icons/hicolor/48x48/apps/sublime-text.png
X-Ubuntu-Gettext-Domain=Sublime Text 3 Editor
```
<!--More -->

这里比较重要的配置是URL和ICON，分别对应快捷方式要执行的命令以及显示的图标，根据需要修改就可以。

这里的Name和Comment都是支持多语言的，你可以通过`Name[语言]=显示内容`的方式来设置它在不同语言环境下的显示效果。例如以下代码用于配置简体中文环境中的特定显示名称：
```
Name[zh_CN]=Sublime Text 3编辑器
```
