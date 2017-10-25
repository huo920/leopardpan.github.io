---
layout: post
title: Java中异常的分类整理
date: 2017-10-24
tags: Java   
---
## 父类:Throwable
>	Throwable是所有异常的父类，位于:java.lang.Throwable
	Java的异常(包括Exception和Error)分为可查的异常（checked exceptions）和不可查的异常（unchecked exceptions）

### 1. 可查异常（编译器要求必须处置的异常）：
<<<<<<< HEAD
>	正确的程序在运行中，很容易出现的、情理可容的异常状况。可查异常虽然是异常状况，但在一定程度上它的发生是可以预计的，而且一旦发生这种异常状况，就必须采取某种方式进行处理。
  
>    除了RuntimeException及其子类以外，其他的Exception类及其子类都属于可查异常。这种异常的特点是Java编译器会检查它，也就是说，当程序中可能出现这类异常，要么用try-catch语句捕获它，要么用throws子句声明抛出它，否则编译不会通过。
=======
>正确的程序在运行中，很容易出现的、情理可容的异常状况。可查异常虽然是异常状况，但在一定程度上它的发生是可以预计的，而且一旦发生这种异常状况，就必须采取某种方式进行处理。
    除了RuntimeException及其子类以外，其他的Exception类及其子类都属于可查异常。这种异常的特点是Java编译器会检查它，也就是说，当程序中可能出现这类异常，要么用try-catch语句捕获它，要么用throws子句声明抛出它，否则编译不会通过。
>>>>>>> 96cdd09505af5f0c5547671bbf26700d80ce9206

### 2. 不可查异常(编译器不要求强制处置的异常):
>	包括运行时异常（RuntimeException与其子类）和错误（Error）。

## 两大子类:     

### 1. Error
<<<<<<< HEAD
>	Error:代表了编译和系统的错误，不允许捕获，位于:java.lang.Error
### 2. Exception
>	Exception:代表了标准Java库方法所激发的异常，位于:java.lang.Exception  

>	Exception 这种异常分两大类运行时异常和非运行时异常(编译异常)。程序中应当尽可能去处理这些异常。
#### 2.1 RuntimeException类及其子类的实例 : 运行时异常
>	对应于编译错误，指Java程序在运行时产生的由解释器引发的各种异常。运行异常可能出现在任何地方，且出现频率很高，因此为了避免巨大的系统资源开销，编译器不对异常进行检查。所以Java语言中的运行异常不一定被捕获。出现运行错误往往表示代码有错误.如NullPointerException(空指针异常)、IndexOutOfBoundsException(下标越界异常)等，这些异常是不检查异常，程序中可以选择捕获处理，也可以不处理。这些异常一般是由程序逻辑错误引起的，程序应该从逻辑角度尽可能避免这类异常的发生。

#### 2.1 Not_RuntimeException类及其子类的实例 : 非运行时异常(无法编译)
>	属于CheckedEcption(可检测异常)。Java编译器利用分析方法或构造方法中可能产生的结果来检测Java程序中是否含有检测异常的处理程序，对于每个可能的可检测异常，方法或构造方法的throws子句必须列出该异常对应的类。在Java的标准包java.lang java.util 和 java.net 中定义的异常都是非运行异常。
	所有RuntimeException以外的异常，类型上都属于Exception类及其子类。从程序语法角度讲是必须进行处理的异常，如果不处理，程序就不能编译通过。如IOException、SQLException等以及用户自定义的Exception异常，一般情况下不自定义检查异常。
=======
	Error:代表了编译和系统的错误，不允许捕获，位于:java.lang.Error
	
### 2. Exception
	Exception:代表了标准Java库方法所激发的异常，位于:java.lang.Exception
	Exception 这种异常分两大类运行时异常和非运行时异常(编译异常)。程序中应当尽可能去处理这些异常。
	
#### 2.1 RuntimeException类及其子类的实例 : 运行时异常
>对应于编译错误，指Java程序在运行时产生的由解释器引发的各种异常。运行异常可能出现在任何地方，且出现频率很高，因此为了避免巨大的系统资源开销，编译器不对异常进行检查。所以Java语言中的运行异常不一定被捕获。出现运行错误往往表示代码有错误.如NullPointerException(空指针异常)、IndexOutOfBoundsException(下标越界异常)等，这些异常是不检查异常，程序中可以选择捕获处理，也可以不处理。这些异常一般是由程序逻辑错误引起的，程序应该从逻辑角度尽可能避免这类异常的发生。

#### 2.1 Not_RuntimeException类及其子类的实例 : 非运行时异常(无法编译)
>属于CheckedEcption(可检测异常)。Java编译器利用分析方法或构造方法中可能产生的结果来检测Java程序中是否含有检测异常的处理程序，对于每个可能的可检测异常，方法或构造方法的throws子句必须列出该异常对应的类。在Java的标准包java.lang java.util 和 java.net 中定义的异常都是非运行异常。
>所有RuntimeException以外的异常，类型上都属于Exception类及其子类。从程序语法角度讲是必须进行处理的异常，如果不处理，程序就不能编译通过。如IOException、SQLException等以及用户自定义的Exception异常，一般情况下不自定义检查异常。
>>>>>>> 96cdd09505af5f0c5547671bbf26700d80ce9206

## 附上思维导图

![这里写图片描述](http://oy2owwigw.bkt.clouddn.com/17-10-24/25344054.jpg)




 如有错误,欢迎指正
