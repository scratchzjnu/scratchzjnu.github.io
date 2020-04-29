---
title: Lubuntu壁纸横跨双显示器的修改
date: 2020-04-29 13:29:54
tags:
---

Lubuntu自18.


1、安装修复脚本

可以在这里查看：https://code.launchpad.net/~hmollercl/stitchwp/+git/stitchwp ，或者也可以直接克隆以下仓库：
```
git clone https://git.launchpad.net/~hmollercl/stitchwp
```
<!-More-->

2、安装依赖
这个脚本的原理就是检查原先的壁纸设置，然后调用identify将它修改为适合双显示器环境的壁纸，最终实现两边“独立”显示的效果。这个identity命令包含在以下包中，可以根据需要选择安装一个，我选择的是这个compact的。
```
Command 'identify' not found, but can be installed with:

sudo apt install graphicsmagick-imagemagick-compat  # version 1.4+really1.3.35-1, or
sudo apt install imagemagick-6.q16                  # version 8:6.9.10.23+dfsg-2.1ubuntu11
sudo apt install imagemagick-6.q16hdri              # version 8:6.9.10.23+dfsg-2.1ubuntu11
```

3、使用方法
先按照常规的方式设置好壁纸，然后执行克隆下来的仓库中的stitchWP.sh。
```
./stitchWP.sh 
convert -size 3286x1080 xc:#000000 -draw "image over 0,0 1366,768 '/home/lester/Pictures/1009758-scenic-wallpaper-1920x1080-laptop.jpg'" -draw "image over 1366,0 1920,1080 '/home/lester/Pictures/1009758-scenic-wallpaper-1920x1080-laptop.jpg'" /home/lester/.config/pcmanfm-qt/lxqt/stitchWP.jpg
pcmanfm-qt --set-wallpaper /home/lester/.config/pcmanfm-qt/lxqt/stitchWP.jpg
QFileSystemWatcher::removePaths: list is empty
QFileSystemWatcher::removePaths: list is empty
```

命令执行之后，稍过一会桌面（我试了几次，大概需要5-10s）就会刷新，显示正常的效果。