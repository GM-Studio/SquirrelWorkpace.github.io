---
title: linux学习笔记(二)用户以及shell
date: 2017.11.17
tags: [Linux,学习笔记]
categories: Linux
---

# 序
当我们对于当前所使用的```shell```表示不满意的时候,我们可以切换其他比较好的```shell```,比如```oh-my-zsh```.接下来我为大家示范一下如何新建一个专门用于新用户的新```shell```环境.

# 内容　
首先我们以两种常见的```Linux```系统环境进行示范和分析.一个是```ubuntu 16.04```另外一个则是```centos 7.x```.这两个```Linux```系统都是大家常用的系统.所以我选取了这两个系统进行示范.由于基于不同的系列.所以所使用的命令略微不同.

## for ubuntu

1.首先更新软件库

```
sudo apt-get update
sudo apt-get upgrade
```
2.安装```zsh```

```
sudo apt-get install zsh
```

3.安装```oh-my-zsh```

```
via curl

sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

via wget

sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

```
4.重启or注销用户
5.重新登录用户就可以使用```oh-my-zsh```了


## for centos

1.首先更新软件库

```
sudo yum update
sudo yum upgrade
```
2.安装```zsh```

```
sudo yum install zsh
```

3.安装```oh-my-zsh```

```
via curl

sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

via wget

sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

```
4.重启or注销用户
5.重新登录用户就可以使用```oh-my-zsh```了

## for 新用户
以上的操作都是针对当前所使用的用户而言,也就是说在当前用户下更改```shell```环境.那么如果我们需要更改到其他用户.抑或着专门为了使用这个```shell```而新建的用户所使用呢?这种情况下应该怎么做呢?

1. 新建一个shell用户
由于ubuntu和centos的不同,新建用户的命令并不一致.
ubuntu
```
sudo adduser oyzsh  //新建名为oyzsh的用户,用于shell
sudo passwd oyzsh 　//更改oyzsh密码
```
由于在ubuntu下,使用useradd命令建立的用户,属于三无用户.即没有密码,没有shell,没有主目录.所以就用adduser来建立了.至于为什么?还有待探究.

centos
```
sudo useradd oyzsh
sudo passwd oyzsh
```

2. 拷贝```oh-my-zsh```的文件到用户主目录
由于之前已经克隆了oh-my-zsh的源代码,可以直接拿过来是使用的.方便又快捷.

```
sudo cp -R /home/sc/.oh-my-zsh /home/oyzsh  //sc为之前所使用用户,前面则为之前使用的用户主目录,后半则是需要用户的主目录
sudo cp -R /home/sc/.zsh* /home/oyzsh //复制有关zsh相关文件到需要用户的主目录.

```

3. 更改目录以及其文件所属的用户以及用户组

```
sudo chgrp -R /home/oyzsh
sudo chown -R /home/oyzsh
```

4. 编辑zshrc文件启用oh-my-zsh

```
sudo vi /home/oyzsh/.zshrc
找到export-path
更改目录到当前用户所属主目录

```
5. 重启或注销使其生效

# 番外总结
不管是什么用户,在使用```shell```环境的时候其实质也是在执行其```shell```脚本.因此用户都应该对这个脚本文件抑或存放这个文件的相关文件夹具有读和可执行的权限.也就是说具备```x```和```r```的权限.不然当使用```shell```的时候,系统就会告诉你权限不够无法使用.
另外,对于文件权限,我们可以利用数字进行简单的标记.

```
x->1
w->2
r->4
```
经过测试,完全可以只需要把```.zshrc```文件拷贝到该新建用户的主目录下,就可以使用了.


# 未完待续
```Linux```学习笔记还尚未结束,敬请期待.......
