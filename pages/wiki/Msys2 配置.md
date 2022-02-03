#### 介绍
> MSYS2 is an updated, modern version of MSYS, both of which are Cygwin (POSIX compatibility layer) forks with the aim of better interoperability with native Windows software.

> The name is a contraction of Minimal SYStem 2, and aims to provide support to facilitate using the bash shell, Autotools, revision control systems and the like for building native Windows applications using MinGW-w64 toolchains.

#### 下载
* <http://msys2.github.io/>

#### 安装
* 解压到任意目录下

#### 与Conemu配置
```
E:\DevTools\msys32\usr\bin\mintty.exe E:\DevTools\msys32\usr\bin\bash --login
```

#### 更换源
```
Open \etc\pacman.d

Add this
## mirror.bit.edu.cn
Server = http://mirror.bit.edu.cn/msys2/REPOS/

```

#### Pacman使用
* 安装 `pacman -S xxx`
* 列出全部软件 `pacman -Qe`
* 更新本地包 `pacman -Syu`
* 搜索包 `pacman -Ss xxx`
* 删除包 `pacman -R xxx`

#### 安装git
* `pacman -S git`

#### 安装python  3.x
* `pacman -S python`

#### 更换zsh
* 安装zsh `pacman -S zsh`
* 更换Shell
```
# 由于无法使用chsh，所以直接从minitty的参数修改：
E:\DevTools\msys32\usr\bin\mintty.exe E:\DevTools\msys32\usr\bin\zsh --login
```
* 建立.zshrc文件 `touch .zshrc`
* 指定Home`~`目录
```
export HOME=/xxx/msys32/mingw32/home/Kenshin
```
* 设定$SHELL参数
```
# vim <MSYS2>/ect/profile
lif [ ! "x${ZSH_VERSION}" = "x" ]; then
  HOSTNAME="$(/usr/bin/hostname)"
  profile_d zsh
  PS1='(%n@%m)[%h] %~ %% '
  SHELL=`which zsh` <------- Add this
elif [ ! "x${POSH_VERSION}" = "x" ]; then
```

#### 安装Oh My Zsh
* `curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh`
* `echo 'export HOME=/xxx/msys32/mingw32/home/Kenshin' >> .zshrc`
* cp ~/.zshrc %USERPROFILE%/.zshrc
* 注意：
> 不清楚是何种原因，msys的根目录设在了`%USERPROFILE%`，而非`msys32/mingw32/home/Kenshin`，所以需要上两步来人为指定HOME目录。

#### 配置Github环境
* 配置
    > 由于不清楚的原因导致无法在$HOME下建立.ssh文件夹，所以需要做以下操作。

    ```
    cd <msys2>/ect
    echo '<home> /home/username' >> fstab
    ```
* 参考
    * <http://qiita.com/nana4gonta/items/622571c66bfe7f1c7150>
    * <http://sourceforge.net/p/msys2/tickets/111/#5fab>

#### 参考
* <http://www.tuicool.com/articles/zmeQfu>
* <http://blog.csdn.net/akof1314/article/details/17842215>
* <http://blog.csdn.net/liyuanbhu/article/details/39397931>
* <http://dantvt.is-programmer.com/posts/63161.html>
* <http://www.bubuko.com/infodetail-562280.html>
* <http://qiita.com/magichan/items/7702d7865deaaca2ad44>