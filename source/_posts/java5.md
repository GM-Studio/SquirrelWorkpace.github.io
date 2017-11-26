---
tile : Java学习笔记(五)性能分析工具使用
date: 2017.11.16
tags: [Java,学习笔记]
categories: Java
---

# 序
我们为什么需要性能分析工具?性能分析能帮助我们什么?我想这几个问题是我这段时间学习Java以来所思考的问题.问题起源于我想针对Java编写的不同方式的读写文件操作的程序进行性能分析,来确定下哪种文件读写操作是比较好的?哪种文件操作方式适合于哪种场合.因此我需要分析程序中方法执行的时间,所使用的内存,所使用的线程等等因素.
那么我用什么软件工具比较好呢？

## 工具使用

### VisualVM for linux
1. ```sudo apt-get install visualvm``` 安装visualvm
2. 打开```IntelliJIEDA```安装```visualvm```的插件
3. 安装好了重启```Idea```,选择用```visualvm```来```run```应用程序.
4. 初次打开```visualvm```,需要选择```visualvm```执行文件的路径.默认是```/usr/bin/jvisualvm```.
5. 然后就可以利用visualvm进行性能分析应用程序了
不知道为什么,我的不能分析简单的应用程序.比如```helloworld```.但是```SpringBoot```的项目却可以分析.有哪位大神可以帮忙分系解决下这个问题?鄙人感激不尽.


### JProfiler for linux

hello world thank your
hey gay  hello world
hello squirrelchen 

## 未完待续
笔记系列尚未完结,未完待续.........
