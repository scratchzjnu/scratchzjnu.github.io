---
title: Hexo部署到Github Pages
date: 2020-04-24 12:01:19
tags: [hexo,github]
---
前置条件：
* 已经安装git, Hexo，并已初始化站点
* 已经将`~/.ssh/id_rsa.pub`中的公钥添加到Github的SSH Keys中。

1、启用Github Pages
登录Github Pages，创建一个名为：username.github.io的仓库，往这仓库里push随便一个文件，因为空仓库是无法启用Github Pages的。

然后在项目的“Settings”页下拉找到Github Pages部分，确保此选项已经启用，同时选择对应的分支，这里图省事就用master了（最好另行创建一个分支来保存Hexo的md文件）。

<!--More -->


2、发布配置信息
修改hexo目录下的_config.yml，在最后的deply部分添加以下代码：
```
deploy:
  type: 'git'
  repository: git@github.com:username/username.github.io.git
  branch: master
  message: update
```

3、安装发布插件
默认安装的Hexo并没有添加用于Git发布的插件，因此直接用hexo deploy发布的时候会出现如下错误：`ERROR Deployer not found: git`,解决方法是安装hexo-deployer-git插件，进入站点目录，输入以下命令：
```
npm install hexo-deployer-git --save
```

4、发布
配置完成后，用`hexo -d`, 或者`hexo deploy`即可。这一操作的实质是将Hexo发布目录的文件做为一个新的版本发布到Github Pages对应的分支中。
