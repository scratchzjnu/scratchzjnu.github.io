---
title: Lubuntu 20.04中自动连接WiFi
date: 2020-04-27 10:03:57
category: 创客与学科教学应用
tags: [ubuntu, 网络]
---

有时候我们出于各种原因都想在系统启动后自动连接到WiFi，在Lubuntu 20.04中，似乎在图形化的配置面板中找不到实现这一设置的方法，如果需要设置，只能通过修改配置文件了。

```
sudo vim /etc/NetworkManager/NetworkManager.conf
```
然后修改其中的managed值为true：
```
[ifupdown]
managed=true
```

