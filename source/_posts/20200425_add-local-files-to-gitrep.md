---
title: 将本地文件加入Git仓库
date: 2020-04-25 20:24:11
tags:
---
#### 初始化本地仓库
将存储了本地文件的目录初始化为Git仓库，添加已有文件并提交。相关代码如下：
```
git init
git add .
git commit -m 'import local files'
```

#### 添加远程仓库
添加远程仓库地址，并拉取远程仓库文件与本地文件合并，相关代码如下：
```
git remote add origin 你的远程库地址（如:git@github.com:username/reponame.git)。
git pull --rebase origin master
```
#### 推送本地库
将本地的当前版本推送到远程仓库，相关代码如下：
```
git push -u origin master
```
