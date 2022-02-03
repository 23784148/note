#### iTerm

```bash
vim ~/.zshrc

enable_proxy() {
    export http_proxy="socks5://127.0.0.1:1080" 
    export https_proxy="socks5://127.0.0.1:1080"
}

disable_proxy() {
    unset http_proxy
    unset https_proxy
}
```

#### Git

```bash
# set
git config --global https.proxy socks5://127.0.0.1:1080
git config --global https.proxy socks5://127.0.0.1:1080

# unset
git config --global --unset http.proxy
git config --global --unset https.proxy
```

#### Git ssh: connect to host github.com port 22: Connection timed out

```bash
# verify ssh is connect
ssh -T git@github.com

# if not connect 
git config --local -e

# change git:// to https://
`url = git@github.com:username/repo.git` →
`url = https://username:password@github.com/username/username.git`
```

#### 参考：

* http://elmagnificogi.github.io/2015/12/03/Git-Proxy/
* https://gist.github.com/laispace/666dd7b27e9116faece6
* http://stackoverflow.com/questions/15589682/ssh-connect-to-host-github-com-port-22-connection-timed-out
* http://honglu.me/2015/11/06/%E7%BB%99iTerm%E7%BB%88%E7%AB%AF%E8%AE%BE%E7%BD%AE%E4%BB%A3%E7%90%86/