---
layout: post
title: Ubuntu上安装MySQL及配置远程登录
date: 2017-10-10
tags: 教程    
---  
## 一.安装MySQL
	
	1. sudo apt-get install mysql-server
	
	2. sudo apt-get install mysql-client
	
	3. sudo apt-get install libmysqlclient-dev

> 注意:安装过程中会提示设置密码和确认密码.记住密码.

> 安装完成之后可以使用如下命令来检查是否安装成功：

	root@root:/# ps aux|grep mysql
	mysql 9323  1.4 10.3 1115748 138308 ?   Ssl  22:34   0:00 /usr/sbin/mysqld
	root  9486  0.0 0.0 21312  928 pts/18  S+  22:34 0:00 grep --color=auto mysql


看到如上结果即安装成功

登陆mysql数据库可以通过如下命令直接登录：
> 之前我设置的密码为:root

	root@root:/# mysql -uroot -proot

> -u 表示选择登陆的用户名，
> -p 表示登陆的用户密码
![这里写图片描述](http://img.blog.csdn.net/20171019005145894?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvaHVvOTIw/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

## 二.配置远程登录

### 1.打开配置文件
	root@root:/# sudo vim /etc/mysql/mysql.conf.d/mysqld.cnf
### 2.修改配置文件
	将bind-address = 127.0.0.1，修改为:0.0.0.0或者注释掉
![这里写图片描述](http://img.blog.csdn.net/20171019005408828?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvaHVvOTIw/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
### 3.添加远程访问权限
	root@root:/# mysql -uroot -proot
	->GRANT ALL PRIVILEGES ON *.* TO 'user'@'%' IDENTIFIED BY 'password' 
		WITH GRANT OPTION;
	->FLUSH PRIVILEGES;
>  上面的user,password可以设置成自己的
![这里写图片描述](http://img.blog.csdn.net/20171019005522345?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvaHVvOTIw/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

### 4.查看是否成功
	 root@root:/# netstat -an | grep 3306
	 tcp      0      0 0.0.0.0:3306         0.0.0.0:*           LISTEN  
> 以上结果表示设置成功   

### 5.重启MySQL
root@root:/# service mysql restart

### 6.测试连接
#### 通过ifconfig找到IP地址
![这里写图片描述](http://img.blog.csdn.net/20171019005623785?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvaHVvOTIw/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

#### 在Navicat上测试连接
![这里写图片描述](http://img.blog.csdn.net/20171019005643741?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvaHVvOTIw/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
