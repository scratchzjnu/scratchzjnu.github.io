---
title: Lubuntu下用命令行建立WiFi连接
date: 2020-04-27 10:10:00
tags: [ubuntu, 网络]
---

要在命令行下连接WiFi到特定的SSID，可以参照以下的步骤：

##### 查看网卡并启用

```
iwconfig

sudo ip link set wlan0 up # 改成自己的无线网卡
```

####  扫描可用热点

```

sudo iw dev wlan0 scan | less  # 分页显示

sudo iw dev wlan0 scan | grep SSID # 仅显示包含SSID的行，即热点列表
```
##### 连接到热点

找到自己要连接的SSID，用以下命令连接：

```
$ sudo iw dev wlan0 connect [网络 SSID] key 0:[WEP 密钥]
```

