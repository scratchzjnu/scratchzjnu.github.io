---
title: 用TravisCI发布Github Pages
date: 2020-04-25 21:49:48
tags: [hexo,github] 
---

Hexo内置了一个deploy的功能，可以通过安装一些发布插件（例如针对git的 `hexo-deployer-git`）来快速部署，此外对于托管在Github的开源项目，也可以使用自动建构工具如TravisCI来发布。

本教程中，我们使用Travis CI来部署Github Pages。它对于开源仓库是免费的，这意味着你的仓库的主分支必须是公开的。如果你的项目不是开源的，那么还是使用`hexo-deployer-git`之类的插件。

#### 项目准备
创建一个名为 username.github.io 的版本库，其中 username 是你在 GitHub 上的用户名。如果你已经上传到了其他的repo，请重新命名这个repo。

将你的Hexo文件夹的文件推送到repository中。public/文件夹默认没有（也不应该）上传，请确保.gitignore文件中包含public/行。文件夹结构应该和这个[repo](https://github.com/hexojs/hexo-starter)大致相似，没有.gitmodules文件。

<!--More -->

#### 连接Travis CI与Github

1. 在[https://github.com/marketplace/travis-ci](https://github.com/marketplace/travis-ci)将Travis CI添加到你的账户中。
2. 转到[Application Settings](https://github.com/settings/installations)，配置Travis CI以访问这个repo。
3. 你会被重定向到Travis页面。
4. 在一个新的[选项卡](https://github.com/settings/tokens)上，生成一个新的令牌，包含repo的作用域。记下令牌的值。
5. 在Travis页面上，转到你的repo的设置。在`Environment Variables`下的`GH-TOKEN`中设置你的用户名与令牌的值，单击添加并保存。
6. 在repo中创建`.travis.yml`文件（与_config.yml、package.json等文件同一目录下），内容如下

	```
	sudo: false
	language: node_js
	node_js:
	  - 10 # use nodejs v10 LTS
	cache: npm
	branches:
	  only:
	    - master # build master branch only
	script:
	  - hexo generate # generate static files
	deploy:
	  provider: pages
	  skip-cleanup: true
	  github-token: $GH_TOKEN
	  keep-history: true
	  on:
	    branch: master
	  local-dir: public
	```
6. 一旦Travis CI完成部署，生成的页面可以在仓库的gh-pages分支中找到。
7. 在你的GitHub repo的设置中，导航到 "GitHub Pages"部分，将源码改为gh-pages分支。
8. 在username.github.io中查看网页。

#### 项目页面
如果你喜欢在GitHub上有一个项目页面，可以参考以下步骤：

1. 在GitHub上导航到你的repo。进入 "设置 "选项卡。更改repository的名称，这样你的blog就可以在username.github.io/repository，repository可以是任何名字，比如blog或hexo。
2. 编辑你的_config.yml，把`root:`值改为`/<repository>/`（必须以斜线开头和结尾，不含括号）。
3. 提交并推送。

