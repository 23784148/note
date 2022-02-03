###MinGW：
####下载：
* <http://sourceforge.net/projects/mingw/>
####配置：
* 由于不做开发环境，所以直接安装即可。（较简单，略去）
###Mintty：
####下载：
* <https://code.google.com/p/mintty/>
> __注意：__下载mintty-1.1.2-msys版本
####配置：
* 将下载的内容解压缩并得到mintty.exe。
* 将mintty.exe复制到MinGW的MSYS\bin目录下，如： F:\kenshin\DevTools\mingw\msys\1.0\bin
* 对F:\kenshin\DevTools\mingw\msys\1.0创建快捷方式，并加入参数： --mintty，如：
> F:\kenshin\DevTools\mingw\msys\1.0\msys.bat --mintty
####运行：
* 直接运行此快捷方式即可。
####MinGW/Mintty中文乱码：
* 输入中文：（修改msys/1.0/etc/inputrc.default和/home/你的用户名/.inputrc为如下内容：）
<pre>
//disable/enable 8bit input
set meta-flag on
set input-meta on
set output-meta on
set convert-meta off
</pre>
* 显示中文：（MinGW设置）
<pre>
alias ls="/bin/ls --color=tty --show-control-chars"
</pre>
* 显示中文：（Mintty设置）
<pre>
Options → Text
Local → C
Character set → GBK
</pre>
####MinGW无法使用ssh的解决办法：
* 将ssh.exe（例如{GIT_HOME}/bin）复制到{MinGW_HOME}\msys\1.0\bin即可。
####使用MSYS-CN替换默认的MSYS：
#####下载：（MSYS-Update.7z）
* <http://code.google.com/p/msys-cn/>
#####替换：
* 解压缩后将bin etc share三个文件夹替换（非覆盖）到{MinGW}\msys\1.0\同名文件夹。
> __注意：__将mintty.exe复制到bin下面。
#####使用：
* 直接运行{MinGW_HOME}\msys\1.0\msys.bat
> __注意：__加上--mintty.exe参数