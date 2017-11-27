---
title: linux学习笔记(二)用户以及shell
date: 2017.11.17
tags: [Linux,学习笔记]
categories: Linux
---

# 序
当我们对于当前所使用的```shell```表示不满意的时候,我们可以切换其他比较好的```shell```,比如```oh-my-zsh```.接下来我为大家示范一下如何新建一个专门用于新用户的新shell环境.

# 内容　
首先我们以两种常见的```Linux```系统环境进行示范和分析.一个是```ubuntu 16.04```另外一个则是```centos 7.x```.这两个```Linux```系统都是大家常用的系统.所以我选取了这两个系统进行示范.由于基于不同的系列.所以所使用的命令略微不同.

## for ubuntu

1. 首先更新软件库

```
sudo apt-get update
sudo apt-get upgrade
```
2. 安装```zsh```

```
sudo apt-get install zsh
```

3. 安装```oh-my-zsh```

```
via curl

sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

via wget

sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

```
4. 重启or注销用户
5. 重新登录用户就可以使用```oh-my-zsh```了


## for centos

1. 首先更新软件库

```
sudo yum update
sudo yum upgrade
```
2. 安装```zsh```

```
sudo yum install zsh
```

3. 安装```oh-my-zsh```

```
via curl

sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

via wget

sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

```
4. 重启or注销用户
5. 重新登录用户就可以使用```oh-my-zsh```了

# 未完待续
```Linux```学习笔记还尚未结束,敬请期待.......
