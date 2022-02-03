### 将某个module中的n个文件打包到一个文件

#### 设定它们的paths：
<pre>
'reset'           : 'module/reset/main'
'reset_model'     : 'module/reset/model'
'reset_view'      : 'module/reset/view'
</pre>

##### 设定它们的依赖：
<pre>
'reset'           :
	deps          : [ 'reset_view', 'reset_model' ]
</pre>

##### 指定r.js的mainconfig：
<pre>
mainConfigFile : './<%= src %>/js/login/config.js',
</pre>