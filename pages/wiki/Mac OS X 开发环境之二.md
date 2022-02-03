#### 开发环境

- `OS X`自带的`python`不含有`pip`，所以需要使用`brew`重新安装`python`
- `brew install python`

#### thefuck

- 介绍 <https://github.com/nvbn/thefuck>
  
- 安装 `pip install thefuck`
  
- 配置
  
  将下面的代码加入到~/.zshrc中
  
  ``` shell
  alias fuck='eval $(thefuck $(fc -ln -1))'
  # You can use whatever you want as an alias, like for Mondays:
  alias FUCK='fuck'
  ```
  
##### git-extras

- 介绍 <https://github.com/tj/git-extras/>
- 安装 `brew install git-extras`

#### cloc

- 介绍 <http://cloc.sourceforge.net/>
  
- 安装 `brew install cloc`
  
- 使用：
  
  ```
  cloc . --exclude-dir=node_modules,dest-extension,publish,vender
  除掉node_modules,dest-extension,publish,vender后统计当前文件夹的代码行数。
  ```

#### autojump

- 介绍 <https://github.com/joelthelion/autojump>
  
- 安装 `brew install autojump`
  
- 使用
  ```
  j <folder>
  jc <folder>
  ```

#### go

- 安装 `brew install go`
  
- 配置
  
  ``` shell
  # go env
  # gopath
  export GOPATH=$HOME/Work/28-GO/01-work
  export PATH=$GOPATH:$PATH
  
  # gobin
  export GOBIN=$GOPATH/bin
  export PATH=$GOBIN:$PATH
  ```
  
#### 其它一些常用工具
  
- <http://wiki.k-zone.cn/post/wiki/babun-pei-zhi>

#### pyenv
- 介绍 <http://v2in.com/pyenv-installation-and-usage.html>
- 安装 `brew install pyenv`
- 配置
```
# add source to ~/.zshrc
export PYENV_ROOT=/usr/local/opt/pyenv
if which pyenv > /dev/null; then eval "$(pyenv init -)"; fi
```
- 使用
```
pyenv install --list # 查看可安装列表
pyenv install x.x.x  # 安装某一版本
pyenv rehash         # 生效
pyenv versiosns      # 查看当前全部的python
pyenv global x.x.x   # 切换某一版本
pyenv local x.x.x    # 只设定某一个目录中的python版本
pyenv shell x.x.x    # 临时设定session中的python版本
```
  