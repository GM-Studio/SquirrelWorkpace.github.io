---
title: Sublime Text(ST) 高级玩法
date: 2017.11.9
tags: [ST,文本编辑器]
categories: ST
---

# ST的个性化配置

## 配置浏览器即时浏览
1. 首先需要安装```SiderBarEnhancements```插件
2. 在```Preferences```菜单栏下选择```Key Bindings``` 打开```User```文件
3. 添加一下代码

```
{ "keys": ["f2"], "command": "side_bar_files_open_with",
        "args": {
            "paths": [],
            "application": "C:/Program Files (x86)/Google/Chrome/Application/chrome.exe",
            "extensions":".*"
        }
 }
```
PS: 在windows下可以打开浏览器的执行文件位置一般都是```exe```
执行程序.在linux下,此举尚行不通.因此这个问题暂时没有办法解决.若有读者有良好的办法,请务必告知.

### 配置markdown环境
1. 安装```Markdown Editing```,```Markdown Preview```，```auto-save``` 插件
2. 按下```ctrl+shift+P```打开快速菜单,键入```’mp’ ```,之后选择```markdown```即可打开你的默认浏览器来预览刚才的内容.
3. 开挂!实现浏览器自动刷新对于浏览器而言,我们让它自动刷新只需在md文件最下面加入一行：

```
<meta http-equiv="refresh" content="0.1">
```
0.1负责表示刷新间隔,单位是秒,个人觉得这是一个比较稳妥的设定值.
太快的话我们难以滚动页面,太慢的话有可能体验很差.
为了不让滚动时编辑的新文字触底,我们在最后一行的刷新代码之上打好几个占空间的行即可.由于空行不会被解析,我们在每一行之前放一个字符#或者打三个以上的减号表示分割线.

实现md文档到html文件的自动更新.这里我们用到了一个叫做```auto-save```的插件,它可以针对一个文档实现空闲x秒后自动保存.我们打开```auto-save```的默认设置和用户设置文件:

```Preference->Package Settings->Auto-save->``` 打开 ```Settings-Defualt```和```Settings-User```
将Default的内容复制粘贴到User里面，然后修改等待时长:

```
  "auto_save_delay_in_seconds": 0.15
```
经过实测,0.15是一个比较能接受的值,不会对磁盘造成频繁读写的影响,延迟也不大.最后就是打开本文档的自动保存功能了:
按下```ctrl+shift+P```打开快速菜单,键入```’auto’```选择到```current file only```按下回车至此,自动保存将在文档更改0.15秒后触发一次,停止自动保存就将上述步骤再做一次即可.现在我们就能够开双侧窗口一边编辑一边预览了~

# 结束
关于Sublime Text的基本常用的知识就写道这里了,若有帮助,请多多支持.若有错误,请务必指正.谢谢大家!
