---
title: Ubuntu 20.04中安装MySQL Server
date: 2020-05-13 20:36:31
category: 创客与学科教学应用
tags: [ubuntu, mysql]
---

自18.10开始，在Ubuntu及衍生版中安装MySQL Server有些不一样，最主要的就是root用户的密码生成机制。在以往版本中，安装向导会让用户设定root的密码，并用mysql_native_password的方式验证，但似乎18.10开始，需要单独使用mysql_secure_installation生成root密码，并且默认采用unix_sockets的验证方式。记录一下安装的过程，供参考。

<!--more-->

首先还是安装mysql-server包，会随同安装一些诸如mysql-client之类的包。
```
sudo apt install mysql-server
```

第二步，初始化root账户的密码，以方便进行后续的操作。
```
sudo mysql_secure_installation
```
此时会出现一个向导，依据其中的提示设定密码，选择是否要禁止远程登录、禁止匿名用户以及是否删除示例数据库等，依据需要选择。

这一步之后，就可以使用root账户登录，但要注意因为认证方式是unix_sockets，所以需要用sudo。
```
sudo mysql -u root -p
```
输入设置的密码后即可进入数据库。

为了后续简化，也可以选择创建一个其它用户。
```
create user 'temp'@'%' identified with mysql_native_password by 'PASSWORD';
grant all privileges on *.* to 'temp'@'%';
flush privileges;
```
如果要限制权限授予的数据库或表，修改其中的“*.*”，如果要设定用户仅限本机访问，可以将“%”改为“localhost”。
这一步之后，退出root账户，即可以改用新创建的帐户登录MySQL Server。


