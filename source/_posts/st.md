---
title: Sublime Text(ST)"The God of Text Editor"安装和使用
date: 2017.11.5
tags: [ST,文本编辑器]
categories: ST
---

# 序
在各种IDE大行其道的今天,如何在极快的时间内打开编辑器写代码变得非常重要.轻量级文本编辑器便显得非常重要.不仅仅打开很快,极大的提高了代码编写的效率.同时也提高了程序员的时间利用率,使其劳动工作更加的高效.那么在各种提高效率的今天,有什么极好的文本编辑器or代码编辑器推荐呢?这就是接下来我推荐的良心软件(bing bu liang xin)Sublime Text.堪称最优秀的代码文本编辑器.(此处应有一万字以及广大程序员的鼓掌).

# Let's learning ST
Q:what's the st?
A:The God of Text Editor

## ST 的安装
### for windows
在windows下安装,在[官方网站](https://www.sublimetext.com/3)下载exe执行安装包,就可以了.

### for linux(基于debian系列的linux)
#### 在linux下安装,就比较麻烦一些.首先需要添加gpg源到apt

```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
```

#### 其次使用https协议链接

```
sudo apt-get install apt-transport-https
```

#### 选择稳定版本

```
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```

#### apt更新及安装

```
sudo apt-get update
sudo apt-get install sublime-text
```

## ST 的激活key
由于st版本经常更新,版本不同导致license key 经常变化,不能统一使用key激活.因此最好按照版本号去百度license key 然后再激活.此处便不再赘述.


# 未完待续
    老司机的车还没开完,车门已焊死,谁都别想下车.未完待续.............
