通过MongoDB的特殊查询符 **$or** 与 **正则表达式** 配合查询：

<pre>
//node.js的正则表达式
query = new RegExp '查询内容', 'i'
</pre>

<pre>
//coffee
exports.search = ( obj, query, random ) ->
    obj.find { '$or' : [{ 'title' : query }, { 'content' : query }] }, ( err, contents ) ->
        if not err 
            exports.emit random + '_contents_search_success', contents
        else
            exports.emit random + '_contents_search_error', err
</pre>
	
<pre>
//node.js
obj.find({ '$or' : [{ 'title' : query }, { 'content' : query }] })
</pre>