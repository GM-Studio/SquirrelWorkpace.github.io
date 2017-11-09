---
title: Sublime Text(ST) 进阶玩法
date: 2017.11.7
tags: [ST,文本编辑器]
categories: ST
---

# ST插件安装
## ST2的package control
键入```ctrl+` ``` 或者 ```ctrl+shift+p``` 输入以下代码

```
   import urllib2,os; pf='Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler( ))); open( os.path.join( ipp, pf), 'wb' ).write( urllib2.urlopen( 'http://sublime.wbond.net/' +pf.replace( ' ','%20' )).read()); print( 'Please restart Sublime Text to finish installation')
```

## ST3的package control
键入```ctrl+` ``` 或者 ```ctrl+shift+p``` 输入以下代码

```
    import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
```


## ST常用插件

### 语言
1. html5(支持html5)
2. JQuery(支持jquery)
3. javascript-api-completions(js标签属性提示)

### 代码编写
1. Emmet(让代码编写的更简单,HTML代码等编写)
2. SublimeLinter(代码校验插件)
3. SublimeCodeIntel(代码自动补全提示等等)
4. Alignment(代码格式化插件)
5. BracketHighlight(括号高亮匹配i)
6. JSFormat(JS代码格式化)

### 注释与文档
1. DocBlockr(生成不同语言的注释)

### 编码格式
1. GBK to UTF8(GBK转UTF8)
2. ConvertToUTF8(UTF8编码转换)

### 文件
1. SiderBarEnhancements(侧边栏增强,可以使用这个完成HTML等文件在浏览器浏览,具体设置请参考以下)
2. FileDiffs(比较文件差异)
3. SublimeTmpl(根据模板快速生成各种文件)
4. PackageResouceViewer(查看包文件)

### 颜色
1. ColorPicker(在sublimetext打开调色盘)
2. Hex-to-HSL-Color(HEX转HSL)

### MarkDown
1. MarkDown Editing(支持markdown的插件)

### Git
1. Git(在sublimetext使用git)

# 未完待续
    老司机的车还没开完,车门已焊死,谁都别想下车.未完待续.............
