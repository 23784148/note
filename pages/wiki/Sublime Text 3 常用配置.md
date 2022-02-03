### Sublimt Text 3 常用插件

#### Package Control
* Homepage  
  <https://packagecontrol.io/installation>
* Show Control  
  ```ctrl+` shortcut or the View > Show Console menu.```

* Install  
  ```
  import urllib.request,os,hashlib; h = '2915d1851351e5ee549c20394736b442' + '8bc59f460fa1548d1514676163dafc88'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
  ```

* Http Proxy  
 ```
 Package Control.sublime-settings
 {
    "http_proxy": "xxxxx",
 }
 ```

* Usage  
  `ctrl + shift + P` or `cmd + shift + P` input `install` or `ip`( install package )

####  Plugins( common )
* BracketHighlighter - 代码匹配，高亮标记，便于查看起始和结束标记
* GitGutter( Modific ) - 高亮上次提交的更改行
* Sublimall( pending ) - 同步插件
* Colorcoder - 高亮变量
* Trailing spaces( Trimmer ) - 高亮多余空格
* FileDiffs - 文件比较
* SideBarEnhancements - 右键菜单增强插件
* Markdown Extended - Markdown 语法高亮（需要配合Monkai Extended）

#### Plugins( Front-end )
* Emmet
* SublimeCodeIntel & Better Completion - 自动补全/代码跳转
* DocBlockr  - 文档插入
* Color Hightlighter - CSS3 取色器
* babel( pending ) - ES6 → ES5
* CSS3( pending )
* ES6 Syntax  - ES6 语法高亮
* Stylus

#### Theme
* SpaceGray
* Monkai Extended
* Predawn
* Material Theme / Material Theme Appbar
* Centurion
* Seti_UI

#### Theme List
* <http://colorsublime.com/>
* <https://longren.io/gigantic-list-of-sublime-text-themes/>

#### Reference
* <http://www.codeceo.com/article/best-sublime-text-plugins.html>
* <http://www.xuanfengge.com/practical-collection-of-sublime-plug-in.html>
* <http://www.cnblogs.com/hykun/p/sublimeText3.html>
* <http://www.oschina.net/translate/20-powerful-sublimetext-plugins>
* <http://div.io/topic/1545>
* <http://chinagdg.org/2016/02/ttt2-seti-ui/>