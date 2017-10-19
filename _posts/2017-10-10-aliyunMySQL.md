---
layout: post
title: 阿里云服务器如何打开端口、MySQL Error2003解决办法
date: 2017-10-10
tags: 教程    
---
#### 此处以安装配置MySQL之后仍旧无法连接为例,出现"ERROR 2003(HY000): Can't connect to MySQL server on 'localhost' (10061)",打开3306端口

### 1.登录阿里云控制台,找到自己的服务器实例
![](http://oy2owwigw.bkt.clouddn.com/17-10-19/71014042.jpg)
### 2.单击更多选项,选择安全组配置
![这里写图片描述](http://oy2owwigw.bkt.clouddn.com/17-10-19/38670539.jpg)
### 3.在出现的页面中单击配置规则
![这里写图片描述](http://oy2owwigw.bkt.clouddn.com/17-10-19/94514064.jpg)
### 4.单击添加安全组规则
![这里写图片描述](http://oy2owwigw.bkt.clouddn.com/17-10-19/68594134.jpg)
### 5.在弹出的页面中填写如下
	端口范围:指定需要的端口
	授权对象:此处设置所有的IP都可访问,可阅读规则,设置响应IP
![这里写图片描述](http://img.blog.csdn.net/20171018234550507?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvaHVvOTIw/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
