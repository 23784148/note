React 学习笔记
================================

介绍
-------------
React是Facebook开源的一套前端框架，它与其它前端框架都不太一样，原因是它没有使用类似MV*的方式，而是直接模块化HTML。（在这点上与Web Component有些类似）
基于这个特点，React可以直接作为其它框架的V的补充，比如：Backbone.js。
React使用了虚拟Dom的方式，要比其它使用脏检查方式的框架更高效。

安装
------------
* 官网下载：<http://reactjs.cn/react/downloads.html>
* npm
> npm install react-tools -g

使用
-----
React库：  
`<script src="react-0.13.0.js"></script>`

如果你使用了JSX方式的话，还需要下面这个解释器：  
`<script src="http://fb.me/JSXTransformer-0.13.0.js"></script>`

npm方式：
* `npm install react-tools -g`（不需要引入`JSXTransformer`库）

自动编译JSX：
* `jsx --watch src/ build/`
* `--harmony`: 启动ES7模式（比如：...props  就许需要在此模式下使用）

Sublime支持：
* <https://github.com/reactjs/sublime-react>
* 快捷键；
    ```
        cdm→  componentDidMount: fn() { ... }
    
       cdup→  componentDidUpdate: fn(pp, ps) { ... }
    
         cs→  var cx = React.addons.classSet;
    
        cwm→  componentWillMount: fn() { ... }
    
        cwr→  componentWillReceiveProps: fn(np) { ... }
    
        cwu→  componentWillUpdate: fn(np, ns) { ... }
    
       cwun→  componentWillUnmount: fn() { ... }
    
         cx→  cx({ ... })
    
        fup→  forceUpdate(...)
    
        gdp→  getDefaultProps: fn() { return {...} } 
    
        gis→  getInitialState: fn() { return {...} } 
    
        ism→  isMounted()
    
      props→  this.props.
    
         pt→  propTypes { ... }
    
        rcc→  component skeleton
    
       refs→  this.refs.
    
        ren→  render: fn() { return ... }
    
        scu→  shouldComponentUpdate: fn(np, ns) { ... }
    
        sst→  this.setState({ ... })
    
      state→  this.state.
    
        trp→  transferPropsTo( ... )
    
    ```


JSX语法规则：
---
<http://facebook.github.io/react/docs/displaying-data.html#jsx-syntax>
##### JXF支持的事件：
<http://facebook.github.io/react/docs/events.html#supported-events>
##### 特点：
* JSX转换为Javascript
  ```
   React.createElement('a', {href: 'http://facebook.github.io/react/'}, 'Hello!') 
   <a href="http://facebook.github.io/react/">Hello!</a>
   ```
* 类似XML语法，如：`<h1>Hello, world!</h1>`
* 支持混入JS语法，如：
    `<div>Hello, {name}!</div>`   
    ```
        <div>
          {
            names.map(function (name) {
              return <div>Hello, {name}!</div>
            })
          }
        </div>
    ```
* 支持插入变量，如：`<div>{arr}</div>`
* 由于class与for是JavaScript的保留字，所以在这里为了避免出错，它们改为：
    > html的class属性需要改为className；  
    > html的for属性需要改为htmlfor；  
    > 除上述两个特例外，JSF的语法基本上与HTML一致。
* JSX使用自定义属性：
    > 加`data-`前缀，如：`<div data-custom-attribute="foo" />`
* 与Dom的区别：<http://reactjs.cn/react/docs/dom-differences.html>
* 为了防止XSS攻击，JSX默认无法插入HTML代码，如需插入的话，使用：`dangerouslySetInnerHTML`
    > <div dangerouslySetInnerHTML={{__html: 'First &middot; Second'}} />
* JSX行内样式（key用驼峰命名方式）  
    <http://reactjs.cn/react/tips/inline-styles.html>
    ```
    var divStyle = {
      color: 'white',
      backgroundImage: 'url(' + imgUrl + ')',
      WebkitTransition: 'all', // 注意这里的首字母'W'是大写
      msTransition: 'all' // 'ms'是唯一一个首字母需要小写的浏览器前缀
    };
    React.render(<div style={divStyle}>Hello World!</div>, mountNode);
    ```

学习笔记
---

##### React.render（入口）：
`React.render( param1, param2 ); `  
* param1：是一个JSX对象。
* param2: 是一个JavaScript DOM对象。
    ```
        React.render(
          <h1>Hello, world!</h1>,
          document.getElementById('example')
        );
    ```

##### React.createClass（组件）:
* 例子：
    ```
    var HelloMessage = React.createClass({
      render: function() {
        return <h1>Hello {this.props.name}</h1>;
      }
    });
    
    React.render(
      <HelloMessage name="John" />,
      document.getElementById('example')
    );
    ```
* {}：表示JavaScript对象。
* {{}}：表示样式对象，例如：
    ```
    <div style={{opacity: this.state.opacity}}>
     Hello {this.props.name}
    </div>
    ```
##### props：
* props是React内置的一个属性，用来从外部（HTML）传递数据到React内部（逻辑）
* props一般做只读用，如果需要改动的话，则需使用state关键字。
* 虽然props也可以被修改，但不建议采用这种方式。
* this.props.children表示组件的全部子节点。如：
```
    var NotesList = React.createClass({
      render: function() {
        return (
          <ol>
          {
            this.props.children.map(function (child) {
              return <li>{child}</li>
            })
          }
          </ol>
        );
      }
    });
    
    React.render(
      <NotesList>
        <span>hello</span>
        <span>world</span>
      </NotesList>,
      document.body
    );
```
* **只有当子节点多余1个时，this.props.children 才是一个数组。**
* getDefaultProps：用来设定props的默认值。
* propTypes：声明props的类型，参考： <http://reactjs.cn/react/docs/reusable-components.html>

##### ref和React.findDOMNode：
* ref用于查找真实html中的定义的属性（ref="MyTextInput"）。
* React.findDOMNode用于查找真实的DOM节点。
* 一般情况下，ref都与React.findDOMNode配合，如下：
```
    var MyComponent = React.createClass({
      handleClick: function() {
        React.findDOMNode(this.refs.myTextInput).focus();
      },
      render: function() {
        return (
          <div>
            <input type="text" ref="myTextInput" />
            <input type="button" value="Focus the text input" onClick={this.handleClick} />
          </div>
        );
      }
    });
    
    React.render(
      <MyComponent />,
      document.getElementById('example')
    );
```
* 上述2个方法均可以用jQuery替代，如：
```
    var MyComponent = React.createClass({
      handleClick: function() {
        $("#myTextInput").focus();
      },
      render: function() {
        return (
          <div>
            <input type="text" id="myTextInput" />
            <input type="button" value="Focus the text input" onClick={this.handleClick} />
          </div>
        );
      }
    });
    
    React.render(
      <MyComponent />,
      document.getElementById('example')
    );
```

##### state：
* 作用于类似props（只读用，不可更改）。如要更改，可以使用state（主要应用在双向绑定），如下：
```
    var LikeButton = React.createClass({
      getInitialState: function() {
        return {liked: false};
      },
      handleClick: function(event) {
        this.setState({liked: !this.state.liked});
      },
      render: function() {
        var text = this.state.liked ? 'like' : 'haven\'t liked';
        return (
          <p onClick={this.handleClick}>
            You {text} this. Click to toggle.
          </p>
        );
      }
    });
    
    React.render(
      <LikeButton />,
      document.getElementById('example')
    );
```
* getInitialState：React内置的方法，主要用于初期化state的值（默认值）。
* setState：用于更新state的值。

##### React的生命周期：
* <http://facebook.github.io/react/docs/component-specs.html#lifecycle-methods>

* Mounting：已插入真实 DOM
* Updating：正在被重新渲染
* Unmounting：已移出真实 DOM
> React 为每个状态都提供了两种处理函数，will 函数在进入状态之前调用，did 函数在进入状态之后调用，三种状态共计五种处理函数。即：
    **Mount两种 ；Update两种； Unmount一种；**

* componentWillMount()
* componentDidMount()
* componentWillUpdate(object nextProps, object nextState)
* componentDidUpdate(object prevProps, object prevState)
* componentWillUnmount()

##### mixins（复用代码） ：
* 语法：`mixins: [SetIntervalMixin]`
    ```
    var SetIntervalMixin = {
      componentWillMount: function() {
        this.intervals = [];
      },
      setInterval: function() {
        this.intervals.push(setInterval.apply(null, arguments));
      },
      componentWillUnmount: function() {
        this.intervals.map(clearInterval);
      }
    };
    
    var TickTock = React.createClass({
      mixins: [SetIntervalMixin], // 引用 mixin
      getInitialState: function() {
        return {seconds: 0};
      },
      componentDidMount: function() {
        this.setInterval(this.tick, 1000); // 调用 mixin 的方法
      },
      tick: function() {
        this.setState({seconds: this.state.seconds + 1});
      },
      render: function() {
        return (
          <p>
            React has been running for {this.state.seconds} seconds.
          </p>
        );
      }
    });
    
    React.render(
      <TickTock />,
      document.getElementById('example')
    );
    ```

##### React与CoffeeScript
//TO DO
##### React与Webpack
//TO DO
##### React与browserify
//TO DO

参考网站
-------
* <https://facebook.github.io/react/>
* <http://react-china.org/>
* <http://reactjs.cn/>
* <http://www.ruanyifeng.com/blog/2015/03/react.html>
* <https://github.com/facebook/react/wiki/Complementary-Tools>
* <https://github.com/jsdf/coffee-react>