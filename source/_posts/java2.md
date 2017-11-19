---
title: Java学习随记(二)
date: 2017-11-03
tags: [Java]
categories: Java学习
---

# String StringBuilder StringBUffer 之间的区别

```
	String 是不可变的对象类,其内容改变的时候,对象也会改变,当其内容发生改变的时候,就会产生一个新的对象包含新的内容,其原来的对象就会被抛弃,被CG给回收掉.而StringBuilder,StringBuffer则是属于可变的对象,其内容改变的时候,其对象也不会改变.都是一个对象.
```

```
	StringBuilder是可变的字符串序列.主要操作是append(),insert()操作 其次不是线程安全的,通常用于单线程的情况.StringBuffer是线程安全的可变的字符串序列.在StringBuffer中append() 插入字符串末端,insert()在指定的位置插入指定的字符.从0开始.初始字符串容量为16.
```

```
	三者在执行速度方面的比较：StringBuilder > StringBuffer > String
```
