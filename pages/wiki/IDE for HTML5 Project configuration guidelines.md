# IDE for HTML5 Project configuration guidelines

### Node.js(NPM)

* Install: <http://nodejs.org/download/>

* Validation: 
<pre>
windows command shell or use sudo (for OSX, *nix, BSD etc)
node --version
npm --version
</pre>

### Grunt & Bower
* Install：
<pre>
windows command shell or use sudo (for OSX, *nix, BSD etc)
npm install grunt-cli bower -g
</pre>

* Validation: 
<pre>
windows command shell or use sudo (for OSX, *nix, BSD etc)
grunt --version
bower --version
</pre>

### Livereload(optional)
* Installing browser extensions: <http://feedback.livereload.com/knowledgebase/articles/86242-how-do-i-install-and-use-the-browser-extensions->

### Setup H5 Project
<pre>
In the H5 Project directory
windows command shell or use sudo (for OSX, *nix, BSD etc)
bower install
npm install
grunt init    //Initialize this project
grunt         //watch and validation this project's source change
grunt server  //run server on brower( Chrome or Firfox )
grunt publish //publish and run this's project on brower( Chrome or Firfox )
</pre>
