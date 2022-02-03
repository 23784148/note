* node.exe下载地址：[http://nodejs.org/download/](http://nodejs.org/download/)  
* 将下载的exe放置到任意文件夹，如 F:\kenshin\DevTools\node-0.8.20  
* 设置环境变量：  
`NODE_HOME = F:\kenshin\DevTools\node-0.8.20`  
* NPM下载地址：[http://nodejs.org/dist/npm](http://nodejs.org/dist/npm)  
* 解压缩到任意文件夹，如：F:\kenshin\DevTools\npm
* 设置NPM下载的Module环境变量：  
`NPM_HOME = F:\kenshin\DevTools\npm`
* 重启系统，并在CMD中进行node.exe与NPM的测试：  
<pre>
node --version
npm --version
如能出现版本号，则说明配置成功。
</pre>

* 设置NPM全局变量（使用npm install xxx -g时下载的目录。根据上面的设置，可知应该下载到 F:\kenshin\DevTools\npm 里面。）  
<http://stackoverflow.com/questions/14742553/npm-local-install-package-to-custom-location>
  + 在cmd中键入：`npm config set prefix "F:\kenshin\DevTools\npm"` （重新设置prefix的位置）   
  + 或者可以直接修改 {当前用户}\.npmrc 文件，在其中直接添加 prefix = F:\kenshin\DevTools\npm 即可。  
  + 设定环境变量: NPM_CONFIG_PREFIX=F:\kenshin\DevTools\npm
* 在CMD中键入：`npm install express -g`，如上述步骤配置无误的话，express就会出现在 F:\kenshin\DevTools\npm\node_modules\express 中。