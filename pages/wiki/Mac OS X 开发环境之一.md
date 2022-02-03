#### HomeBrew

- Site 

  - <http://brew.sh/>

- Install 

  >  /usr/bin/ruby -e "$(curl -fsSLhttps://raw.githubusercontent.com/Homebrew/install/master/install)"
- Usage

  - Update

    - `brew update`

      * When update error, message like `error: The following untracked working tree files would be overwritten by merge:`

        ``` shell
          cd /usr/local
          git fetch origin
          git reset --hard origin/master
        ```

    - Upgrade

      * `brew upgrad xxx` -- update xxx
      * `brew upgrade`    -- update all

    - Outdated

      - `brew outdated`

    - Cleanup

      * ` brwe clean `

    - Install any version
      - `brew install homebrew/boneyard/<formula>`
      - `brew tap homebrew/boneyard` and `brew install <formula>` or `brew install https://raw.githubusercontent.com/Homebrew/homebrew-boneyard/master/<formula>.rb`

      - ​	

        Example

        > brew unlink go
        >
        > brew tap homebrew/versions
        >
        > brew install go15
        >
        >  (auto) export PATH=$PATH:/usr/local/opt/go15/libexec/bin

      - 说明

        - 上面的例子安装 `go 1.5` 版本（当前环境是 `go 1.6` ）

        - 安装在 `/usr/local/Cellar/go15` 而非 `/usr/local/Cellar/go`下。

        - 当使用 `brew list` 时，会发现 有两个包：`go` and `go15`

        - 至此，新版本 go15 已经可以使用了，如果想要切换回 1.6版本，需要执行：

          > brew unlink go15
          >
          > brew link go

    - Other Usage

      - `brew search formula` - 搜索软件包
      - `brew install formula` - 安装软件包
      - `brew remove formula` - 移除软件包
      - `brew cleanup formula` -  清除旧包
      - `brew list` - 列出已安装的软件包
      - `brew update` - 更新 Homebrew
      - `brew upgrade` - 升级软件包
      - `brew home formula` - 用浏览器打开
      - `brew info formula` - 显示软件内容信息
      - `brew deps formula` - 显示包的依赖
      - `brew server` - 启动 web 服务器，访问 http://localhost:4567 管理包
      - `brew -h` - 帮助

    - Reference

      - <http://stackoverflow.com/questions/10762859/brew-update-the-following-untracked-working-tree-files-would-be-overwritten-by>
      - <https://segmentfault.com/q/1010000000466369>
      - <https://github.com/Homebrew/homebrew-boneyard>
      - <https://github.com/Homebrew/homebrew-versions>

#### Homebrew Case

- Install

  - `brew install caskroom/cask/brew-cask`

- Usage

  - `brew case install <package>`

- Plugs

  - <https://github.com/sindresorhus/quick-look-plugins>
  - `brew cask install qlcolorcode qlstephen qlmarkdown quicklook-json betterzipql suspicious-package`

- Install frome local

  ``` shell
  curl <package_url>
  unzip
  mv <package_url> /opt/homebrew-cask/Caskroom/
  ln -s /opt/homebrew-cask/Caskroom/<package_url>/xxx.qlgenerator /Users/kenshin/Library/QuickLook/xxx.qlgenerator
  ```

#### ZSH

- Install `brew install zsh`
- Change bash to ZSH `chsh -s /bin/zsh`

#### Oh-my-zsh

- `curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh`
- Custom Oh-my-zsh 
  - <http://wiki.k-zone.cn/post/wiki/ohmyzsh-for-os-x-pei-zhi>
- Reference
  - <http://site.douban.com/125980/widget/notes/4884065/note/232038698/>
  - <http://leeiio.me/bash-to-zsh-for-mac/>
  - <https://github.com/sjl/oh-my-zsh>
  - <https://github.com/robbyrussell/oh-my-zsh/wiki/themes>
  - <http://foocoder.com/blog/wo-zai-yong-de-macruan-jian-2.html/>
  - <http://site.douban.com/125980/widget/notes/4884065/note/232038698/>
  - <http://www.hksilicon.com/kb/cn/articles/43024/MacOSX-shellzsh>
- Usage Custom Package
  - `vim ~/.zshrc`
  - modify `PATH` to `export PATH=/usr/local/bin;$PATH` ( Change the user environment variable to first PATH  )

#### iTerm2

- Download APP from <http://iterm2.com/>
- Theme <https://github.com/altercation/solarized/tree/master/iterm2-colors-solarized>

#### Gem

- Install
  - download `https://rubygems.org/pages/download`
  - unzip
  - `cd rubygems-2.4.6`
  - `sudo ruby setup.rb`
- Install gem package from local
  - `gem install --local <full-path>`

