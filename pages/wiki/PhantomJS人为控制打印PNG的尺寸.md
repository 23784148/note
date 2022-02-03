#### server-client：
<pre>
page.onCallback = ( result ) ->
    console.log 'callback = ' + JSON.stringify result
    #set size
    page.viewportSize = { width : result.width + 50, height : result.height + 200 }
</pre>

#### client-server：
<pre>
if ( typeof window.callPhantom === 'function' ) {
	window.callPhantom({ 'width' : xxx, 'height' : xxx });
}
</pre>