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


## ST 的常用快捷键

### 选择类

```
    Ctrl+D 选中光标所占的文本，继续操作则会选中下一个相同的文本。

    Alt+F3 选中文本按下快捷键，即可一次性选择全部的相同文本进行同时编辑。举个栗子：快速选中并更改所有相同的变量名、函数名等。

    Ctrl+L 选中整行，继续操作则继续选择下一行，效果和 Shift+↓ 效果一样。

    Ctrl+Shift+L 先选中多行，再按下快捷键，会在每行行尾插入光标，即可同时编辑这些行。

    Ctrl+Shift+M 选择括号内的内容（继续选择父括号）。举个栗子：快速选中删除函数中的代码，重写函数体代码或重写括号内里的内容。

    Ctrl+M 光标移动至括号内结束或开始的位置。

    Ctrl+Enter 在下一行插入新行。举个栗子：即使光标不在行尾，也能快速向下插入一行。

    Ctrl+Shift+Enter 在上一行插入新行。举个栗子：即使光标不在行首，也能快速向上插入一行。

    Ctrl+Shift+[ 选中代码，按下快捷键，折叠代码。

    Ctrl+Shift+] 选中代码，按下快捷键，展开代码。

    Ctrl+K+0 展开所有折叠代码。

    Ctrl+← 向左单位性地移动光标，快速移动光标。

    Ctrl+→ 向右单位性地移动光标，快速移动光标。

    shift+↑ 向上选中多行。

    shift+↓ 向下选中多行。

    Shift+← 向左选中文本。

    Shift+→ 向右选中文本。

    Ctrl+Shift+← 向左单位性地选中文本。

    Ctrl+Shift+→ 向右单位性地选中文本。

    Ctrl+Shift+↑ 将光标所在行和上一行代码互换（将光标所在行插入到上一行之前）。

    Ctrl+Shift+↓ 将光标所在行和下一行代码互换（将光标所在行插入到下一行之后）。

    Ctrl+Alt+↑ 向上添加多行光标，可同时编辑多行。

    Ctrl+Alt+↓ 向下添加多行光标，可同时编辑多行。
```

### 编辑类
```
    Ctrl+J 合并选中的多行代码为一行。举个栗子：将多行格式的CSS属性合并为一行。

    Ctrl+Shift+D 复制光标所在整行，插入到下一行。

    Tab 向右缩进。

    Shift+Tab 向左缩进。

    Ctrl+K+K 从光标处开始删除代码至行尾。

    Ctrl+Shift+K 删除整行。

    Ctrl+/ 注释单行。

    Ctrl+Shift+/ 注释多行。

    Ctrl+K+U 转换大写。

    Ctrl+K+L 转换小写。

    Ctrl+Z 撤销。

    Ctrl+Y 恢复撤销。

    Ctrl+U 软撤销，感觉和 Gtrl+Z 一样。

    Ctrl+F2 设置书签

    Ctrl+T 左右字母互换。

    F6 单词检测拼写
```

### 搜索类
```
    Ctrl+F 打开底部搜索框，查找关键字。

    Ctrl+shift+F 在文件夹内查找，与普通编辑器不同的地方是sublime允许添加多个文件夹进行查找，略高端，未研究。

    Ctrl+P 打开搜索框。举个栗子：1、输入当前项目中的文件名，快速搜索文件，2、输入@和关键字，查找文件中函数名，3、输入：和数字，跳转到文件中该行代码，4、输入#和关键字，查找变量名。

    Ctrl+G 打开搜索框，自动带：，输入数字跳转到该行代码。举个栗子：在页面代码比较长的文件中快速定位。

    Ctrl+R 打开搜索框，自动带@，输入关键字，查找文件中的函数名。举个栗子：在函数较多的页面快速查找某个函数。

    Ctrl+： 打开搜索框，自动带#，输入关键字，查找文件中的变量名、属性名等。

    Ctrl+Shift+P 打开命令框。场景栗子：打开命名框，输入关键字，调用sublime text或插件的功能，例如使用package安装插件。

    Esc 退出光标多行选择，退出搜索框，命令框等。
```

### 显示类
```
    Ctrl+Tab 按文件浏览过的顺序，切换当前窗口的标签页。

    Ctrl+PageDown 向左切换当前窗口的标签页。

    Ctrl+PageUp 向右切换当前窗口的标签页。

    Alt+Shift+1 窗口分屏，恢复默认1屏（非小键盘的数字）

    Alt+Shift+2 左右分屏-2列

    Alt+Shift+3 左右分屏-3列

    Alt+Shift+4 左右分屏-4列

    Alt+Shift+5 等分4屏

    Alt+Shift+8 垂直分屏-2屏

    Alt+Shift+9 垂直分屏-3屏

    Ctrl+K+B 开启/关闭侧边栏。

    F11 全屏模式

    Shift+F11 免打扰模式
```


## ST插件安装
### ST2的package control
键入```ctrl+` ``` 或者 ```ctrl+shift+p``` 输入以下代码

```
   import urllib2,os; pf='Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler( ))); open( os.path.join( ipp, pf), 'wb' ).write( urllib2.urlopen( 'http://sublime.wbond.net/' +pf.replace( ' ','%20' )).read()); print( 'Please restart Sublime Text to finish installation')
```

### ST3的package control
键入```ctrl+` ``` 或者 ```ctrl+shift+p``` 输入以下代码

```
    import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
```


### ST常用插件

#### 语言
1. html5(支持html5)
2. JQuery(支持jquery)
3. javascript-api-completions(js标签属性提示)

#### 代码编写
1. Emmet(让代码编写的更简单,HTML代码等编写)
2. SublimeLinter(代码校验插件)
3. SublimeCodeIntel(代码自动补全提示等等)
4. Alignment(代码格式化插件)
5. BracketHighlight(括号高亮匹配i)
6. JSFormat(JS代码格式化)

#### 注释与文档
1. DocBlockr(生成不同语言的注释)

#### 编码格式
1. GBK to UTF8(GBK转UTF8)
2. ConvertToUTF8(UTF8编码转换)

#### 文件
1. SiderBarEnhancements(侧边栏增强,可以使用这个完成HTML等文件在浏览器浏览,具体设置请参考以下)
2. FileDiffs(比较文件差异)
3. SublimeTmpl(根据模板快速生成各种文件)
4. PackageResouceViewer(查看包文件)

#### 颜色
1. ColorPicker(在sublimetext打开调色盘)
2. Hex-to-HSL-Color(HEX转HSL)

#### MarkDown
1. MarkDown Editing(支持markdown的插件)

#### Git
1. Git(在sublimetext使用git)


## ST的个性化配置

### 配置浏览器即时浏览
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
    老司机的车还没开完,车门已焊死,谁都别想下车.未完待续.............
