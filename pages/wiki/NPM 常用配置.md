#### Website:
* <https://www.npmjs.com/>

#### Update:
* update `self`  `npm update -g npm` | `npm install -g npm`
* update `xxx` `npm update xxx` | `npm update xxx -g`

#### Usage:

##### Install:

* `npm install xxxx`
* Parameter:
  * -g `npm install -g xxx` -- install xxx to golbal folder
  * --dev-save `npm install xxx --dev-save` -- install xxx to packgage.json::devDependencies
  * --dev `npm install xxx --dev-save`  -- install xxx to packgage.json::dependencies
  * install same version `npm install xx@xx.xx.xx`

##### Link:
* `npm link xxxx`

  > when you more project, use `npm install -g aaa bob` and use `npm link aaa`  link global aaa  to current folder.

#### NPM registry manager(nrm):
* Website:
  * `https://github.com/Pana/nrm`

* Install:
  * `npm install nrm -g`

* Example:
  * `nrm test`   -- show the response time for one or all registries
  * `nrm ls`     -- show all nrm registries
  * `nrm use xxx` -- selected xxx registry

* Usage:
  * ```
    Usage: nrm [options] [command]

      Commands:

        ls                           list all the registries
        use <registry>               change registry to registry
        add <registry> <url> [home]  add one custom registry
        del <registry>               delete one custom registry
        home <registry> [browser]    open the homepage of registry with optional browser
        test [registry]              show the response time for one or all registries
        help                         print this help

      Options:

        -h, --help     output usage information
        -V, --version  output the version number
    ```

#### NPM client for China(cnpm):

* Website:
  * <http://npm.taobao.org/>
  * <https://github.com/cnpm/cnpm>
* Install:
  * `npm install -g cnpm --registry=https://registry.npm.taobao.org`
* Example:
  * change `npm` to `cnpm` e.g. `cnpm install xxx`
* Usage:
  * support `all commands` except `npm publish`.

#### Reference:

* <http://www.tuicool.com/articles/VB7nYn>
* <http://blog.nodejitsu.com/npm-cheatsheet/>
* <http://package.json.nodejitsu.com/>
