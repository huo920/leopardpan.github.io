---
layout: post
title: 使用Intellij idea配置Tomcat
date: 2017-04-22
tags: 教程    
---  


## 1.创建项目
![](http://oy2owwigw.bkt.clouddn.com/17-10-22/2541346.jpg)

## 2.选择类型
> 在2和3处选择自己安装的jdk和Tomcat,**勾选4中的Web Application**
![](http://oy2owwigw.bkt.clouddn.com/17-10-22/90389437.jpg)

## 3.填写项目名,完成项目创建
![](http://oy2owwigw.bkt.clouddn.com/17-10-22/61370345.jpg)

## 4.进入项目界面,点击右上角图标:Project Structure
![](http://oy2owwigw.bkt.clouddn.com/17-10-22/26093723.jpg)

## 5.选择Modules下的Sources配置,在web目录下新建classes,lib两个文件夹
![](http://oy2owwigw.bkt.clouddn.com/17-10-22/11244255.jpg)

## 6.选择Sources右边的Paths配置,将路径改为刚刚新建的classes文件夹
![](http://oy2owwigw.bkt.clouddn.com/17-10-22/30868442.jpg)

## 7.在选择Paths边上的Dependencies配置,在选中Module source后点击右上角加号,选择第一个JARS or directories,在弹出页面中选择刚刚新建的lib文件夹
![](http://oy2owwigw.bkt.clouddn.com/17-10-22/21682238.jpg)

## 8.在弹出页面选择Jar Directoty,将lib目录作为存放jar包的文件夹
![](http://oy2owwigw.bkt.clouddn.com/17-10-22/37952426.jpg)

## 9.选择左侧的Artifacts,在右侧勾选连个复选框,最后点击右下角OK
![](http://oy2owwigw.bkt.clouddn.com/17-10-22/14751667.jpg)

## 10.测试运行
![](http://oy2owwigw.bkt.clouddn.com/17-10-22/66558487.jpg)

# 附:Tomcat配置
## 1.如图点击
![](http://oy2owwigw.bkt.clouddn.com/17-10-22/99042873.jpg)

## 2.选择Tomcat安装目录,端口有冲突的话修改默认端口,选择默认浏览器
![](http://oy2owwigw.bkt.clouddn.com/17-10-22/87194388.jpg)

## 3.添加默认地址
![](http://oy2owwigw.bkt.clouddn.com/17-10-22/61542218.jpg)

