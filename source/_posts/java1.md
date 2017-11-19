---
title: Java学习随记(一)
date: 2017-11-04 
tags: [Java]
categories: Java学习
---

# Java随记一

## 问
Java开发中经常有在项目路径```Build Path```中导入jar包 或者在```/WEB-INF/lib```目录下导入jar包.那么这两种有什么区别呢?为什么我在```Build Path```导入的包在诸如tomcat中运行的时候不起作用呢？

## 答
通俗的讲是和```classLoader```有关,对于纯java项目,它不存在```WEB-INF```目录,所以在引入jar包的时候一般都是通过```buildpath```直接引入.例如我要引入```Spring3X```,那么先定义一个```user library```然后通过build path引入.
纯java项目使用的本地自己的``JRE```,那么```classLoader```在加载jar和class时候是分开的,对于我们自己编写的class,会在```APP_HOME/bin```下.导入的jar包或者```user library```的配置信息会出现在```APP_HOME/.classpath```文件中,```ClassLoader```会很智能去加载这些classes和jar.其实是由于不同的类加载器决定的,对于服务器容器诸如tomcat之类的,是有它自己的类加载器的.

```java
1.common CommonClassLoader
2.server CatalinaClassLoader
3.shared SharedClassLoader
4.webapps webappClassLoader(加载WEB-INF下的jar)
```

因此是完全不会加载本地java项目的jar包的,也就是说在```build path```下导入的jar包并不会加载.但是存在于```/WEB-INF/lib```下的jar就会加载了.这就是说为什么我们在部署JavaEE项目时.使用框架jar包会在```/WEB-INF/lib```下.
