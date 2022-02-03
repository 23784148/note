#### oh my zsh常用插件

- 插件
  
  `bundler osx brew autojump colored-man zsh_reload atom zsh-syntax-highlighting git git-flow git-extras ruby gem python pip node npm bower`
  
- 第三方（zsh-syntax-highlighting）
  
  - 介绍 
    
    <http://naxoc.net/2014/02/02/syntax-highlighting-commands-with-zsh/>
    
  - 安装
    
    ``` 
    git clone git://github.com/zsh-users/zsh-syntax-highlighting.git
    write source /path/to/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh to .zshrc
    add zsh-syntax-highlighting to .zshrc plugins
    reload zsh source ~/.zshrc
    ```
    
  



- .zshrc配置参考
  
  ``` shell
  # custom alias
  alias cls='clear'
  alias zshrc='at ~/.zshrc'
  
  alias -s html=at
  alias -s js=at
  alias -s css=at
  alias -s coffee=at
  ```
  
- Powerline-Shell
  
  - <http://wiki.k-zone.cn/post/wiki/babun-pei-zhi>
  - powerline-shell font `git clone https://github.com/powerline/fonts.git`
  - `cd fonts` & `./install.py`
  - iTerm2 > Preferences > `ASCII fonts` & `non-ASCII fonts` set `xxx for power line`
  
- Color Folder
  
  ``` shell
  brew install coreutils
  
  add to ~/.zshrc
  export PATH="/usr/local/opt/coreutils/libexec/gnubin:$PATH"
  export MANPATH="/usr/local/opt/coreutils/libexec/gnuman:$MANPATH"
  
  git clone git@github.com:seebi/dircolors-solarized.git
  echo 'eval `dircolors ~/<path>/dircolors-solarized/dircolors.xxx`' >> ~/.zshrc
  ```
  



- 参考
  
  - <http://cenalulu.github.io/linux/mac-powerline/>
  - <https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins-Overview#build-tools>
  - <https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins>
  - <http://foocoder.com/blog/wo-zai-yong-de-macruan-jian-2.html>
  - <http://blog.163.com/xh_ding/blog/static/193903289201462211626537/>
  - <http://macshuo.com/?p=676>
  - <http://segmentfault.com/a/1190000000513010>
  - <https://github.com/altercation/solarized/tree/master/iterm2-colors-solarized>
  - <http://www.gocalf.com/blog/make-mac-better-for-development.html>
  - <https://github.com/seebi/dircolors-solarized>
  - <http://www.gocalf.com/blog/make-mac-better-for-development.html>
  
