---
layout: post
title: Ubuntu上安装MySQL及配置远程登录
date: 2017-10-10
tags: 教程    
---

#Ubuntu16.04上安装MySQL5.7及配置远程登录
##安装MySQL
	
	1. sudo apt-get install mysql-server
	
	2. sudo apt-get install mysql-client
	
	3. sudo apt-get install libmysqlclient-dev

>注意:安装过程中会提示设置密码和确认密码.记住密码.

>安装完成之后可以使用如下命令来检查是否安装成功：

	root@root:/# ps aux|grep mysql
	mysql 9323  1.4 10.3 1115748 138308 ?   Ssl  22:34   0:00 /usr/sbin/mysqld
	root  9486  0.0 0.0 21312  928 pts/18  S+  22:34 0:00 grep --color=auto mysql


看到如上结果即安装成功

登陆mysql数据库可以通过如下命令直接登录：
>之前我设置的密码为:root

	root@root:/# mysql -uroot -proot

>-u 表示选择登陆的用户名，
>-p 表示登陆的用户密码
<img src="/images/posts/UbuntuMySQL/01.png"> 

##配置远程登录

###1.打开配置文件
	root@root:/# sudo vim /etc/mysql/mysql.conf.d/mysqld.cnf
###2.修改配置文件
	将bind-address = 127.0.0.1，修改为:0.0.0.0或者注释掉
<img src="/images/posts/UbuntuMySQL/02.png">
###3.添加远程访问权限
	root@root:/# mysql -uroot -proot
	->GRANT ALL PRIVILEGES ON *.* TO 'user'@'%' IDENTIFIED BY 'password' 
		WITH GRANT OPTION;
	->FLUSH PRIVILEGES;
>上面的user,password可以设置成自己的
<img src="/images/posts/UbuntuMySQL/04.png">

###4.查看是否成功
	 root@root:/# netstat -an | grep 3306
	 tcp      0      0 0.0.0.0:3306         0.0.0.0:*           LISTEN  
>以上结果表示设置成功   

###5重启MySQL
root@root:/# service mysql restart

###6测试连接
####通过ifconfig找到IP地址
<img src="/images/posts/UbuntuMySQL/03.png">

####在Navicat上测试连接
<img src="/images/posts/UbuntuMySQL/05.png">