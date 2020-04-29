---
title: Ubuntu中安装Sublime Text 3
date: 2020-04-25 21:13:35
tags: [linux]
---

Sublime Text 3是优秀的跨平台文本编辑器，也是程序员的神器，它的插件及其管理器的功能应该让人过目不忘。介绍一下Ubuntu中的安装方法。

#### 添加GPG Key
先在终端中用以下命令下载并添加GPG Key:
```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
```
再安装`apt-transport-https`来为apt增加https源的访问功能：
```
sudo apt-get install apt-transport-https
```

<!--More -->

#### 添加源
官方提供了两个版本的源，Stable是稳定版，Dev是开发版，用于新功能（但也许不稳定）的体验，地址分别是：

Stable
```
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```
Dev
```
echo "deb https://download.sublimetext.com/ apt/dev/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```

#### 安装Sublime Text 3
更新apt的软件源并且安装，可以使用以下命令：
```
sudo apt-get update
sudo apt-get install sublime-text
```
