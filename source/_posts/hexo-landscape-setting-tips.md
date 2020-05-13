---
title: Hexo Landscape主题的一些配置记录
date: 2020-04-26 10:31:51
category: 创客与学科教学应用
tags: [hexo]
---

Landscape是Hexo自带的默认主题，这里记录一些常见的修改配置。当然，Hexo有很多漂亮的主题，你也可以clone相关主题的repo添加到themes目录，并在hexo的_config.yml的theme项中来指定。

1. Hexo创建的贴子是以标题作为文件名了，多了容易乱，如何处理？  

	可以在Hexo的`_config.yml`中修改"#Writing"部分的`new_post_name"，例如以下语句是将其设置为“年月日-标题”的方式：
	```
	new_post_name: :year:month:day_:title.md # File name of new posts
	```
	<!--More-->
2. 贴子怎么添加多个标签？  
	要为贴子添加多个标签，需要在生成的贴子源文件的frontmatter部分，用以下方式设置tags，如果觉得不大好记，就记住放一个Python的列表好了。
	```
	tags: [tag1, tag2, tag3]
	```
3. 如何修改默认的banner图？ 
	最简单的方式就是将自己的banner图替换landscape\source\images目录下的banner.jpg，文件。
	实际的配置选项是在主题目录下source\css中的`_variables.styl`，修改Header中的几个选项：
	```
	banner-height = 138px
	banner-url = "images/banner.png"
	```
4. 如何修改Hexo网站的语言？ 
	默认的中文语言包位于landscape\language中，名为`zh-CN.yml`，更名为`zh-Hans.yml`，将其中未翻译好的继续翻译完。
	然后修改Hexo目录下的`_config.yml`，修改以下项：
	```
	language: zh-Hans
	```
