---
layout: post
title: 阿里云服务器如何打开端口、MySQL Error2003解决办法
date: 2017-10-10
tags: 教程    
---

#关于阿里云服务器如何打开端口的解决办法

##此处以安装MySQL之后为例,打开3306端口

###1.登录阿里云控制台,找到自己的服务器实力
<img src="/images/posts/aliyunMySQL/00.png"> 

###2.单击更多选项,选择安全组配置
<img src="/images/posts/aliyunMySQL/01.png"> 

###3.在出现的页面中单击配置规则
<img src="/images/posts/aliyunMySQL/02.png"> 

###4.单击添加安全组规则
<img src="/images/posts/aliyunMySQL/03.png"> 

###5.在弹出的页面中填写如下
	端口范围:指定需要的端口
	授权对象:此处设置所有的IP都可访问,可阅读规则,设置响应IP
<img src="/images/posts/aliyunMySQL/04.png"> 