---
title: Linux中禁用触控板与Trackpoint
date: 2020-04-25 21:15:14
tags: [linux,thinkpad]
---

家里一个比较老的Thinkpad X220跑不动Windows 10了，就装了个Lubuntu。经常会碰到触控板，所以打字的时候挺不方便的，我个人使用的第一台笔记本电脑是Thinkpad A21m，之后沿着T41、R51一路过来（再之后转到Macbook和其它各种好看的轻薄本了），所以还是比较习惯Trackpoint的，所以打算禁用触控板。
相关的一些方法如下：

<!--More -->

#### 禁用触控板与Trackpoint

如果要同时禁用触控板与Trackpoint，可以使用以下方法：
```
sudo modprobe -r psmouse # 禁用
sudo modprobe -a psmouse # 启用
```
以上操作仅在当前会话有效，如果要长期禁用，可以：
`sudo vi /etc/modeprobe.d/blacklist.conf` 然后在blacklist.conf的最后加入以下语句
```
blacklist psmouse
```
此外，在BIOS中进行设置也是一种方法，但不太推荐，以免太长时间不用忘记还以为是硬件故障。

#### 仅禁用触控板

如果需要单独对触控板进行禁用与启用，可以用以下方法：
```
synclient TouchpadOff=1 # 禁用
synclient TouchpadOff=0 # 启用
```
此时尽管触控板禁用了，但Trackpoint依然可用。比较符合我的需求，同样这一方法也仅在当前会话中有效。如果需要一直保持这一配置，可以在`/etc/rc.local`中添加上述代码。

即`sudo vim /etc/rc.local`, 在最后增加：`synclient TouchpadOff=1`，保存退出

2020.4.29更新：
Lubuntu中rc.local不起作用了，可以在开始菜单中找到“首选项”/“LXQT设置”/“会话配置”，在其中的“命令”中加入上述命令。
