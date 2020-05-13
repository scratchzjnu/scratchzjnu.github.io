---
title: 编辑Linux的hosts文件
date: 2020-04-25 21:13:50
category: 创客与学科教学应用
tags: [linux,hosts]
---

默认情况下，Linux中的hosts文件存储于`/etc/hosts`，直接编辑这个文件就可以完成hosts记录的修改。这里说几个常用的操作方法，不然一句话一个贴子实在有点过意不去。

#### 查看hosts文件内容
最简单的是终端中用`cat /etc/hosts`即可，输出样例如下：
```
lester@lubuntu:~/Documents/hexo$ cat /etc/hosts
127.0.0.1	localhost
127.0.1.1	lubuntu
```

<!--More -->

#### 修改hosts文件内容

如果就在其中增加一行记录，那么最简单的方法是使用echo重定向到此文件，例如：
```
sudo echo 127.0.0.1 baidu.com >> /etc/hosts
```
如果涉及大批量的修改，那么还是找个编辑器来修改，例如：
```
vim /etc/hosts
```
