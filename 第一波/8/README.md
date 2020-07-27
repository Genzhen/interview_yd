## 1 如何处理异常捕获？项目如何管理模块？

> 1、try..catch
> 2、 window.onerror

使用 webpack 管理模块

## 2 手动实现一个 Promisify 函数

promisify 是 node 的 utils 模块中的一个函数，它作用就是为了转换最后一个参数是回调函数的函数为 promise 函数，且回调函数中有两个参数：error 和 data
使用方法如下:

```javascript
// 使用前
fs.readFile("./index.js", (err, data) => {
  if (!err) {
    console.log(data.toString())
  }
  console.log(err)
})
// 使用promisify后
const readFile = promisify(fs.readFile)
readFile("./index.js")
  .then((data) => {
    console.log(data.toString())
  })
  .catch((err) => {
    console.log("error:", err)
  })
```

```javascript
// const newFn = promisify(fn)
// newFn(a) 会执行Promise参数方法
function promisify(fn) {
  return function (...args) {
    // 返回promise的实例
    return new Promise(function (reslove, reject) {
      // newFn(a) 时会执行到这里向下执行
      // 加入参数cb => newFn(a)
      args.push(function (err, data) {
        if (err) {
          reject(err)
        } else {
          reslove(data)
        }
      })
      // 这里才是函数真正执行的地方执行newFn(a, cb)
      fn.apply(null, args)
    })
  }
}
```

## 3 说一下 webpack 与 gulp 的区别（源码角度）?优缺点？

1）gulp
gulp 强调的是前端开发的工作流程，我们可以通过配置一系列的 task，定义 task 处理的事务（例如文件压缩合并、雪碧图、启动 server、版本控制等），然后定义执行顺序，来让 gulp 执行这些 task，从而构建项目的整个前端开发流程。简单说就一个 Task Runner，模块化不是他强调的东西，他旨在规范前端开发流程。

2）webpack
webpack 是一个前端模块化方案，更侧重模块打包，我们可以把开发中的所有资源（图片、js 文件、css 文件等）都看成模块，通过 loader（加载器）和 plugins（插件）对资源进行处理，打包成符合生产环境部署的前端资源。webpack 更是明显强调模块化开发，而那些文件压缩合并、预处理等功能，不过是他附带的功能。

## 4 RN 如何调用原生的一些功能、如何和原生进行通信?RN 为什么能在原生中绘制成原生组件?native 提供了什么能力给 RN?

## 5 React/Redux 中哪些功能用到了哪些设计模式

## 6 webpack 如何配 sass，需要配哪些 loader，配 css 需要哪些 loader?说一下 webpack 中 css-loader 和 style-loader 的区别，file-loader 和 url-loader 的区别?

1）安装依赖包

```javascript
npm install node-sass sass-loader --save-dev
```

2）打开 webpack.config.js 在 loaders 里面加

```javascript
{
  test: /\.scss\$/,
  loaders: ["style", "css", "sass"]
}
```

3)在组件里样式里写或者新建 scss 文件

```javascript
<style lang="scss" scoped></style>
```

##### css-loader 和 style-loader 区别

css-loader 会处理 import / require（） @import / url 引入的内容。
style-loader 就是将 css-loader 解析后的内容挂载到 html 页面当中。是通过一个 JS 脚本创建一个 style 标签，里面包含一些样式。

##### file-loader 和 url-loader

## 7 是否熟悉 Node，主要做过哪些业务，平时用过什么包？介绍一下 node 核心模块（主要是 stream）

## 8 React 遇到性能问题一般在哪个生命周期里解决？shouldComponentUpdate 是为了解决什么问题?

## 9 一个对象数组，每个子对象包含一个 id 和 name，React 如何渲染出全部的 name？在哪个生命周期里写？其中有几个 name 不存在，通过异步接口获取，如何做？渲染的时候 key 给什么值？可以使用 index 吗？用 id 好还是 index 好？

## 10 介绍 Redux 数据流的流程?说一下单向数据流有什么好处？Redux 怎么实现属性传递，介绍下原理?Redux 状态管理器和变量挂载到 window 中有什么区别?

## 11 16.X 中 props 改变后在哪个生命周期中处理？如何解决 props 层级过深的问题？componentWillReceiveProps 的触发条件是什么？

## 12 如何配置把 js、css、html 单独打包成一个文件?一般怎么组织 CSS（Webpack）?webpack 如何用 localStorage 离线缓存静态资源？

## 13 概述异步编程模型？在 ES6 中有哪些解决异步的方法？说一下 JavaScript 异步解决方案的发展历程以及优缺点

## 14 前端怎么做单元测试

## 15 实现一个打点计时器

- 1.从 start 至 end,每隔 100 毫秒 console.log 一个数字，每次数字增幅为 1
- 2.返回的对象中需要包含一个 cancel 方法，用于停止定时操作
- 3.第一个数字需要立即输出

  1). settimeout 方式

```javascript
function count(start, end) {
  if (start <= end) {
    console.log(start++)
    st = setTimeout(function () {
      count(start, end)
    }, 100)
  }
  return {
    cancel: function () {
      clearTimeout(st)
    },
  }
}
count(1, 10)
```

2). setInterval 方式

```javascript
function count(start, end) {
  console.log(start++)
  var timer = setInterval(function () {
    if (start <= end) {
      console.log(start++)
    } else {
      clearinterval(timer)
    }
  }, 100)
  return {
    cancel: function () {
      clearinterval(timer)
    },
  }
}
count(1, 10)
```

## 16 react 异步渲染的概念,介绍 Time Slicing 和 Suspense？

##### Time Slicing

##### Suspense

React 的 Suspense 功能，简单说就是让组件渲染遇到需要异步操作的时候，可以无缝地“悬停”（suspense）一下，等到这个异步操作有结果的时候，再无缝地继续下去。
这里所说的异步操作，可以分为两类：

- 异步加载代码
- 异步加载数据

## 17 介绍下原型链？说一下对原型链的理解，画一个经典的原型链图示？使用原型链如何实现继承？说一下使用原型最大的好处？

#### 原型链

当一个对象调用自身不存在的属性/方法时，就会去自己 [proto] 关联的前辈 prototype 对象上去找，如果没找到，就会去该 prototype 原型 [proto] 关联的前辈 prototype 去找。依次类推，直到找到属性/方法或 undefined 为止。从而形成了所谓的“原型链”。

## 18 说一下 React.Component 和 Ract.PureComponent 的区别

PureComponent 改变了生命周期方法 shouldComponentUpdate，并且它会自动检查组件是否需要重新渲染。这时，只有 PureComponent 检测到 state 或者 props 发生变化时，PureComponent 才会调用 render 方法，因此，你不用手动写额外的检查，就可以在很多组件中改变 state,PureComponent 会对 props 和 state 进行浅层比较，并减少了跳过必要更新的可能性。

React.PureComponent 与 React.Component 几乎完全相同，但 React.PureComponent 通过 prop 和 state 的浅对比来实现 shouldComponentUpate()。

- 继承 PureComponent 时，不能再重写 shouldComponentUpdate，否则会引发警告

- 继承 PureComponent 时，进行的是浅比较，也就是说，如果是引用类型的数据，只会比较是不是同一个地址，而不会比较具体这个地址存的数据是否完全一致

## 19 用 html、css、js 模拟实现一个下拉框，使得下拉框在各个浏览器下的样式和行为完全一致，说出你的设计方案，并且重点说明功能设计时要考虑的因素。

## 20 请解释 JSONP 的工作原理?jsonp 为什么不支持 post 方法?除了 jsonp、postmessage 后端控制，怎么实现跨页面通讯?

##### 工作原理

首先在客户端注册一个 callback，然后把 callback 的名字传给服务器。此时，服务器先生成 json 数据，然后以 javascript 语法的方式，生成 function，function 名字就是传递上来 I 带参数 jsonp。最后将 json 数据直接以入参的方式，放置 function 中，这样就生成 js 语法的文档，返回给客户端。客户端浏览器，解析 script 变迁，并执行返回 javascript 文档，此时数据作为参数，传入了客户端预先定义好的 callback 函数里。简单的说，就是利用 script 标签没有跨域限制的“漏洞”来达到与第三方通讯的目的

##### jsonp 为什么不支持 post 方法

这种跨域方式其实与 ajax XmlHttpRequest 协议无关了。

##### 跨页面通讯

###### 同源页面之间的通信

1. BroadCast Channel
2. Service Worker
3. LocalStorage
4. Shared Worker
5. IndexedDB
6. window.open + window.opener

###### 非同源页面之间的通信

而对于非同源页面，则可以通过嵌入同源 iframe 作为“桥”，将非同源页面通信转换为同源页面通信。

总结

- 广播模式：Broadcast Channe / Service Worker / LocalStorage + StorageEvent
- 共享存储模式：Shared Worker / IndexedDB / cookie
- 口口相传模式：window.open + window.opener
- 基于服务端：Websocket / Comet / SSE 等

## 21 介绍下 React 高阶组件，和普通组件有什么区别，适用什么场景

##### 高阶函数

高阶函数是一个函数，它接收函数作为参数或将函数作为输出返回
实际开发中的高阶函数

- Array 的 map 、reduce 、filter 等方法
- Object 的 keys 、values 等方法

##### 高阶组件

高阶组件就是一个函数，且该函数接受一个组件作为参数，并返回一个新的组件
一个高阶组件只是一个包装了另外一个 React 组件的 React 组件。

```javascript
function withHoc(WrappedComponent) {
  return class extends Component {
    render() {
      return <WrappedComponent />
    }
  }
}
```

##### 适用场景

- 代码复用，逻辑抽象，抽离底层准备（bootstrap）代码
- 渲染劫持
- State 抽象和更改
- Props 更改

  https://www.jianshu.com/p/0aae7d4d9bc1

## 22 单例、工厂、观察者项目中实际场景？JavaScript 写一个单例模式，可以具体到某一个场景？

##### 单例

单例要求一个类有且只有一个实例，提供一个全局的访问点。因此它要绕过常规的控制器，使其只能有一个实例，供使用者使用，而使用着不关心有几个实例，因此这是设计者的责任。
单例比较适用于一个对象和其他系统进行交互。
单例有点类似于一个小组的小组长，在一段时间内只有一个小组长，有小组长来指定组员的工作，分配和协调和组员的工作。

JS 的单例应该视作初始化后不被修改的变量，如此看来，其实单例模式是 JS 里应用最广泛的设计模式使用 CDN 引入的所有库文件的入口都是单例，比如大名鼎鼎的 jQuery。

1. 需要对页面资源进行统一调度。最典型的就是弹窗，单个弹窗当然没问题，但如果用户还没看清第一个弹窗的时候，第二个弹窗又来了，两个弹窗不管是覆盖还是叠加，体验都是极为糟糕的，这种时候就应该将所有弹窗放到一个单例下进行管理。
2. 需要复用对象以节约资源。比如使用 webSocket 与后台通信的时候。webSocket 虽然使用方便，但是多个 webSocket 连接会占用大量的服务端资源，因此，一个页面内绝对不能初始化多个接口相同的 webSocket。最好的实现是：同一个浏览器内不管有多少页面，都共享同一个连接，不过，维持连接的页面关闭的时候，其他页面需要及时发起新的连接来保持通信，这样的功能需要后端的支持才能达到。

##### 工厂模式

jQuery 也是一个典型的工厂模式，你给他一个参数，他就给你返回符合参数 DOM 对象。那 jQuery 这种不用 new 的工厂模式是怎么实现的呢？其实就是 jQuery 内部帮你调用了 new 而已，jQuery 的调用流程简化了就是这样:

```javascript
;(function () {
  var jQuery = function (selector) {
    return new jQuery.fn.init(selector) // new一下init, init才是真正的构造函数
  }

  jQuery.fn = jQuery.prototype // jQuery.fn就是jQuery.prototype的简写

  jQuery.fn.init = function (selector) {
    // 这里面实现真正的构造函数
  }

  // 让init和jQuery的原型指向同一个对象，便于挂载实例方法
  jQuery.fn.init.prototype = jQuery.fn

  // 最后将jQuery挂载到window上
  window.$ = window.jQuery = jQuery
})()
```

工厂模式的名字就很直白，封装的模块就像一个工厂一样批量的产出需要的对象。常见工厂模式的一个特征就是调用的时候不需要使用 new，而且传入的参数比较简单。但是调用次数可能比较频繁，经常需要产出不同的对象，频繁调用时不用 new 也方便很多。一个工厂模式的代码结构如下所示:

```javascript
function factory(type) {
  switch (type) {
    case "type1":
      return new Type1()
    case "type2":
      return new Type2()
    case "type3":
      return new Type3()
  }
}
//上述代码中，我们传入了type，然后工厂根据不同的type来创建不同的对象。
```

> 实例: 弹窗组件
> 下面来看看用工厂模式的例子，假如我们有如下需求：

我们项目需要一个弹窗，弹窗有几种：消息型弹窗，确认型弹窗，取消型弹窗，他们的颜色和内容可能是不一样的。
针对这几种弹窗，我们先来分别建一个类：

```javascript
function infoPopup(content, color) {}
function confirmPopup(content, color) {}
function cancelPopup(content, color) {}
```

如果我们直接使用这几个类，就是这样的:

```javascript
let infoPopup1 = new infoPopup(content, color)
let infoPopup2 = new infoPopup(content, color)
let confirmPopup1 = new confirmPopup(content, color)
```

每次用的时候都要去 new 对应的弹窗类，我们用工厂模式改造下，就是这样：

```javascript
// 新加一个方法popup把这几个类都包装起来
function popup(type, content, color) {
  switch (type) {
    case "infoPopup":
      return new infoPopup(content, color)
    case "confirmPopup":
      return new confirmPopup(content, color)
    case "cancelPopup":
      return new cancelPopup(content, color)
  }
}
```

然后我们使用 popup 就不用 new 了，直接调用函数就行:

```javascript
let infoPopup1 = popup("infoPopup", content, color)
```

## 23 setInterval 需要注意的点?定时器为什么是不精确的?setTimeout(1)和 setTimeout(2)之间的区别

## 24 介绍 instanceof 原理，并手动实现

instanceof 主要用于判断某个实例是否属于某个类型，也可用于判断某个实例是否是其父类型或者祖先类型的实例。

instanceof 主要的实现原理就是只要右边变量的 prototype 在左边变量的原型链上即可。因此，instanceof 在查找的过程中会遍历左边变量的原型链，直到找到右边变量的 prototype，如果查找失败，则会返回 false。

```javascript
function instanceof(left, right) {
  const rightVal = right.prototype
  const leftVal = left.__proto__
  // 若找不到就到一直循环到父类型或祖类型
  while (true) {
    if (leftVal === null) {
      return false
    }
    if (leftVal === rightVal) {
      return true
    }
    leftVal = leftVal.__proto__ // 获取祖类型的__proto__
  }
}
```

## 25 JavaScript 是什么范式语言? for..in 和 object.keys 有什么区别?

js 是多范式语言：命令式、函数式、面向对象
Object.keys()：返回一个数组，数组值为对象自有的属性，不会包括继承原型的属性
for in :遍历对象可枚举属性，包括自身属性，以及继承自原型的属性

## 26 请实现一个 JSON.stringfy?请实现一个 JSON.parse?

其实 JSON.parse/JSON.stringify 还是有很多局限性

- 忽略 undefined
- 忽略 Symbol
- 无法序列化 function，也会忽略
- 无法解决循环引用，会报错
- 深层对象转换爆栈

```javascript
function json2str(o) {
  let arr = []
  const fmt = function (s) {
    if (typeof s == "object" && s !== null) return json2str(s)
    return /^(string)$/.test(typeof s) ? `"${s}"` : s
  }
  for (var i in o) arr.push(`"${i}":${fmt(o[i])}`)
  return `{${arr.join(",")}}`
}
const obj = {
  name: "Lily",
  age: 30,
  tel: "132xxxxxxxx",
  address: { city: "beijing", district: "haidian", detail: "dddddddd" },
}
const generatedData = json2str(obj)
```

## 27 介绍 class 和 ES5 的类以及区别?介绍 defineProperty 方法，什么时候需要用到

## 28 添加原生事件不移除为什么会内存泄露，还有哪些地方会存在内存泄漏？

## 29 JavaScript 中如何模拟实现方法的重载

## 30 数组有哪些方法？讲讲区别跟使用场景？尽可能多的写出判断数组的方法
