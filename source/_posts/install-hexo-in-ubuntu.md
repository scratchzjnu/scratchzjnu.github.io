---
title: 在Ubuntu中安装Hexo
date: 2020-04-25 22:06:28
tags: [linux,ubuntu]
---

Hexo是一个静态站点生成程序，使用的开发技术是Nodejs。在Ubuntu及衍生版中的安装方法如下：

#### 安装NodeJS
```
sudo apt install nodejs, npm
```
更换淘宝镜像：
```
sudo npm --global config set registry https://registry.npm.taobao.org
```
查看并检查配置：
```
npm config list
```
<!--More -->

#### 安装版本更新工具N：
```
sudo npm install n -g
```
更新版本，显示installed:版本号，表示更新成功。
```
sudo n stable
```

#### 安装Hexo
```
sudo npm install -g hexo-cli
```
