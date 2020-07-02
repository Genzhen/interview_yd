## 按要求实现 rightView 函数

> js-二叉树的右视图.js

## 请手写实现一个拖拽

## Fiber 算法原理，相比之前的 stack 算法哪些方面做了优化？

## 单点登录实现原理

单点登录是在多个应用系统中，用户只需要登录一次就可以访问所有相互信任的应用系统的保护资源，若用户在某个应用系统中进行注销登录，所有的应用系统都不能再直接访问保护资源，像一些知名的大型网站，如：淘宝与天猫、新浪微博与新浪博客等都用到了这个技术。

有一个独立的认证中心，只有认证中心才能接受用户的用户名和密码等信息进行认证，其他系统不提供登录入口，只接受认证中心的间接授权。间接授权通过令牌实现，当用户提供的用户名和密码通过认证中心认证后，认证中心会创建授权令牌，在接下来的跳转过程中，授权令牌作为参数发送给各个子系统，子系统拿到令牌即得到了授权，然后创建局部会话。

## React 如何实现双向绑定，并抽象成公共组件

## 按要求完成题目

a)在不使用 vue、react 的前提下写代码解决一下问题
一个 List 页面上，含有 1000 个条目的待办列表，现其中 100 项在同一时间达到了过期时间，需要在对应项的 text-node 里添加“已过期”文字。需要尽可能减少 dom 重绘次数以提升性能。
b)尝试使用 vue 或 react 解决上述问题

## node 如何进行跨域通信

设置可访问源 Access-Control-Allow-Origin

## React SSR 实现过程？原理是什么？有什么注意事项？

## Node 性能如何进监控以及优化？如何做错误监控（运行时与其他？如何生成日志，日志等级

## Node 的适用场景以及优缺点是什么？

## 请说明 JavaScript 进行压缩、合并、打包实现的原理是什么？为什么需要压缩、合并、打包？分别列出一种常用工具或插件

## 说出前端框架设计模式(MVVM 或 MVP 又或 MVC)的含义以及原理

## 开发环境热更新的优化方式

## 请用 JavaScript 代码实现事件代理

## 有这样一个函数 A,要求在不改变原有函数 A 功能以及调用方式的情况下，使得每次调用该函数都能在控制台打印出“HelloWorld”

function A() {
console.log("调用了函数 A");
}

## 按照调用实例，实现下面的 Person 方法

```javascript
Person("Li")
// 输出： Hi! This is Li!

Person("Dan").sleep(10).eat("dinner")
// 输出：
// Hi! This is Dan!
// 等待 10 秒..
// Wake up after 10
// Eat dinner~

Person("Jerry").eat("dinner").eat("supper")
// 输出：
// Hi This is Jerry!
// Eat dinner~
// Eat supper~

Person("Smith").sleepFirst(5).eat("supper")
// 输出：
// 等待 5 秒
// Wake up after 5
// Hi This is Smith!
// Eat supper
```

## 按要求完成代码

```javascript
const timeout = (ms) =>
  new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve()
    }, ms)
  })
const ajax1 = () =>
  timeout(2000).then(() => {
    console.log("1")
    return 1
  })
const ajax2 = () =>
  timeout(1000).then(() => {
    console.log("2")
    return 2
  })
const ajax3 = () =>
  timeout(2000).then(() => {
    console.log("3")
    return 3
  })
const mergePromise = (ajaxArray) => {
  // 1,2,3 done [1,2,3] 此处写代码 请写出 ES6、ES3 2 中解法
}
mergePromise([ajax1, ajax2, ajax3]).then((data) => {
  console.log("done")
  console.log(data) // data 为[1,2,3]
})
// 执行结果为：1 2 3 done [1,2,3]
```

## 请修改代码能跳出死循环

```javascript
while (1) {
  switch ("yideng") {
    case "yideng":
    //禁止直接写一句break
  }
}
```

## Vue 双向绑定原理以及路由钩子在 Vue 生命周期的体现

## 如何记录前端再用户浏览器上发生的错误并汇报给服务器？

## 有 1000 个 dom，需要更新其中的 100 个，如何操作才能减少 dom 的操作？

## 多个 tab 只对应一个内容框，点击每个 tab 都会请求接口并渲染到内容框，怎么确保频繁点击 tab 但能够确保数据正常显示？

## 商城的列表页跳转到商品的详情页，详情页数据接口很慢，前端可以怎么优化用户体验？

## 说一下 Css 预处理器，Less、Sass 等 带来的好处？

- 为了减少 CSS 代码冗余，为 CSS 提供样式复用机制，提高 CSS 代码的可维护性

## 原生实现 ES5 的 Object.create()方法

Object.create()方法创建一个新对象，使用现有的对象来提供新创建的对象的**proto**。

```javascript
fuction creat(obj){
  function F(){}
  F.prototype = obj
  retrun new F()
}

```

## 请实现鼠标点击页面中的任意标签，alert 该标签的名称(注意兼容性)

> getItem.html

## 请说明 Html 布局元素的分类有哪些？并描述每种布局元素的应用场景

- 块状元素：display:block 标签独占一行，可指定宽、高

- 内联元素：display:inline 标签在一行内，宽度与高度由内容决定，只有在内容超过 HTML 的宽度时，才会换行

- 内联块状元素：display:inline-block 同时具备内联元素、块状元素的特点，和其他元素都在一行上,元素的高度、宽度、行高以及顶和底边距都可设置

> 常用的块状元素有：

```javascript
<div>、<p>、<h1>...<h6>、<ol>、<ul>、<dl>、<table>、<address>、<blockquote> 、<form>
```

> 常用的内联元素有：

```javascript
<a>、<span>、<i>、<em>、<strong>、<label>、<q>、<var>、<cite>、<code>
```

> 常用的内联块状元素有：

```javascript
 <img>、<input>
```

## 尾递归实现

## Vuex 和 localStorage 的区别

- localStorage 存储的值能够永久的存储在浏览器上。不管是重新打开新窗口还是重启，同一个浏览器上的相同域名下，localStorage 的值一直在。
- sessionStorage 存储的值依赖于当前窗口(当前会话), 只要当前窗口不关闭，它存储的数据就一直在。一旦关闭窗口或者打开新窗口，sessionStorage 之前存储的数据就会消失。
- 相比 localStorage 和 sessionStorage，vuex 存储的数据可以即时更新到，当前项目下的所有引用了该数据的组件。但是如果刷新页面的话，vuex 存储的值会重置，而 localStorage 和 sessionStorage 存储的值不会重置。

## Vue 计算属性和普通属性的区别?描述下自定义指令(你是怎么用自定义指令的)
