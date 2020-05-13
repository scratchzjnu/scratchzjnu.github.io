---
title: 修改Falkon浏览器的User Agent信息
date: 2020-04-27 15:23:19
tags: [ubuntu, 网络,]
---

现在很多的网站为了确保用户体验，限制了允许使用的浏览器软件及其版本，一旦检测到不属于目标的浏览器就禁止用户登录，并“友情”给出一个浏览器软件下载的链接。但实际上，如果浏览器的内核是一样的，最终显示的效果也基本是一致的，所以对这样的处理有点不好理解。退回去说，显示效果不佳，或者某些功能缺失，总比什么也不能看好吧。

现在很多浏览器都使用Chromium、Firefox的内核，本质其实可以归为同一类，因此有时候也比较无奈。比如我们有个网站，开发商限定了Safari、Chrome以及360的某些版本，这样一来，其它的第三方浏览器，如QQ浏览器虽然也与360一样使用了Chromium内核，但就无法登录了。我在Lubuntu中使用的是Falkon就总是受这种歧视，所以决定修改一下User Agent伪装成其它浏览器吧。

<!--More-->

##### 获取目标浏览器的User-Agent标识
这个可以从网络上搜索一下，我是在[UA检测](https://useragent.buyaocha.com/)这个网站获取的，这个工具可以查看自己浏览器的User-Agent，同时也给出了常用浏览器的UA列表。

直接复制了列表中排在第一个的Mac版Chrome的UA:`Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/73.0.3683.75 Safari/537.36`。

##### 修改Falkon设置
在“首选项”中找到“其它”，选择“更改浏览器标识”下方的“User Agent管理器”，这里所做的修改有两个作用域：更改全局User Agent, 为指定网站使用不同的User Agent，我们选择的是下者。添加一个记录，分别输入网站的域名以及目标User Agent标识字符串。

保存设置并重启Falkcon后就没有这个提示了。