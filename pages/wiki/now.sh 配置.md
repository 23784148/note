### Introduce

> now 允许您轻松、快速和可靠地将 JavaScript（Node.js）或 Docker 支持的网站、应用程序和服务带到云中。
>
> 支持常见的环境，如： Node.js / PHP / Go and more

### Install

`npm install -g now`

### Usage

> 以 Node.js 为例，建立任一个 Node.js + Express 的页面，包含若干 js / html / css 等

- `package.json` 里面需要有 `start` 节点；
- 在此文件夹中直接执行 `now` 即可；

### Important

> 不清楚什么原因，导致无法使用 now.json 作为配置文件（以 Node.js 为例，其它环境未测试）

直接在当前文件夹中执行 `now` 即可，它会自行判断环境，同时需要有 `start` 节点。

>  `package.json` 的 `name`

如果没有 `now.json` 的话，每次执行 `now` 它会判断 `package_name` 如果值相同，则视为同一个 Project

> 如何使用 env

`now -e NODE_ENV=production` 即可

> 容器默认会隔一段时间重启，为了不让容器重启，执行下面的命令

`now scale oneindex-yckkdopvtv.now.sh 1`

> 免费的 now.sh 应用会自动打开 `_src` 可以查看任意代码

`https://<domain>/_src`

> 尽量保证 `package.json` → `scripts` 只保留 `start`  如：

```
"scripts": {
    "start": "node app"
  },
```

避免不必要的错误。（当 now 发生 error 时，请留意 `scripts` ）

### Custom Domain

>  `now alias xxx-mralaoilhl.now.sh <domain> `

**重点之一**

- Shadowsocks 走全局代理；
- 命令行所在的环境需要翻墙；

**重点之二**

第一次绑定会失败，但会提示你如何绑定，需要设定 TXT / CNAME ，如下：

![Xnip2019-04-18_11-50-29.jpg](https://i.loli.net/2019/04/18/5cb7f45f97899.jpg)

![Xnip2019-04-18_11-51-52.jpg](https://i.loli.net/2019/04/18/5cb7f45f7a773.jpg)

设定完毕后，重新执行

 `now alias xxx-mralaoilhl.now.sh <domain>`

稍等片刻会有类似 _Success! xxx_ 之类的提示，即配置完毕；

**重点之三**

如果配置时出现了 403 错误，需要确保 **重点之一** 或稍后再试；

**重点之四**

每次使用 `now` 都会生成一个类似 `<package_name>-54sdvjj2xf.now.sh` 名字的地址，需要每次都要重新设置对应的 `<domain>`

### Workflow

> 重新梳理一下整个的发布流程

- `now -e NODE_ENV=production` 成功后，会得到一个  `<package_name>-54sdvjj2xf.now.sh` 的域名；
- `now scale xxxx-mralaoilhl.now.sh 1`  不自动反复重启容器 _疑似第一次执行即可_
-  `now alias https://xxxx-mralaoilhl.now.sh <domain>` 重新设置对应域名

### Reference

- <https://subei.me/archives/58/>
- <https://flycode.co/archives/219363>
- <https://ngif.cn/detail/82.html>