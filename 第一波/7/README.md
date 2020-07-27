## 1 脚手架具体做了哪些事？Webpack 做了什么？使用 webpack 构建时有无做一些自定义操作？你是怎么使用 webpack 进行开发环境配置的？

## 2 import { Button } from 'antd'，打包的时候只打包 button，分模块加载，是怎么做到的?如何实现分模块打包（多入口）？

## 3 pm2 怎么做进程管理，进程挂掉怎么处理?不用 pm2 怎么做进程管理?master 挂了的话 pm2 怎么处理?

## 4 多个组件之间如何拆分各自的 state，每块小的组件有自己的状态，它们之间还有一些公共的状态需要维护，这如何思考？state 是怎么注入到组件的，从 reducer 到组件经历了什么样的过程？

## 5 说一下服务端渲染，SSR

## 6 koa 中 response.send、response.rounded、response.json 发生了什么事，浏览器为什么能识别到它是一个 json 结构或是 html?koa-bodyparser 如何解析 request

## 7 说一下 Vuex 的原理以及自己的理解？为什么要用 Vuex 或者 Redux，不要说为了保存状态？

## 8 介绍 React 设计思路，它的理念是什么？对 React 的看法，它的优缺点，使用过程中遇到的问题，如何解决的?和 Vue 比较有什么异同？

## 9 Redux 中间件是什么东西？接受几个参数？柯里化函数两端的参数具体是什么东西？Redux 中间件是怎么拿到 store 和 action？然后怎么处理？使用过的 Redux 中间件？redux 请求中间件如何处理并发？

## 10 说下对作用域的理解，解释下 let 和 const 的块级作用域？var、let、const 的区别? let 块作用域是怎么实现的?const 是怎么实现，动手实现一下

## 11 接入 Redux 过程？绑定 connect 的过程？connect 的原理

## 12 React 怎么做数据的检查和变化？

## 13 JavaScript 执行过程分为哪些阶段?词法作用域和 this 的区别？什么是作用域链？说一下变量的作用域链

## 14 怎么定义 vue-router 的动态路由？怎么获取传过来的动态参数？

## 15 loadsh 深拷贝实现原理？详细分析下

## 16 一个活动项目里包含多个活动，Webpack 如何实现单独打包某个活动？Webpack 里面的插件时怎么实现的？Webpack 抽取公共文件是怎么配置的

## 17 对 async、await 的理解，内部原理是怎样的？async、await 如何进行错误捕获?promise 跟 async await 的区别，介绍使用场景？ 动手实现 Async/Await

## 18 React 组件中怎么做事件代理？它的原理是什么？

## 19 以最小的改动解决以下代码的错误(可以使用 ES6)

```javascript
const obj = {
name:"jsCoder",
skill:["es6","react","angular"],
say:function(){
for(var i = 0,len = this.skill.length;i<len;i++){
setTimeout(function(){
console.log('No.' + i + this.name);
console.log(this.skill[i]);
console.log('----------------');
},0);
console.log(i);
}
}
}
obj.say();

/\*
期望得到下面的结果
1
2
3
No.1 jsCoder
es6

---

No.2 jsCoder
react

---

No.3 jsCoder
angular
\*/
```

## 20 实现一个倒计时,setInterval 实现的话，如何消除时间误差

## 21 哪些方法会触发 react 重新渲染？重新渲染 render 会做些什么？React 如何避免 renderd 的触发?

## 22 对无状态组件的理解？说一下 React 有状态组件与无状态组件区别，以及为什么要用，它的优缺点？

## 23 实现 Function 原型的 bind 方法，使得以下程序最后能输出“success”

```javascript
function Animal(name, color) {
  this.name = name
  this.color = color
}
Animal.prototype.say = function () {
  return `I'm a ${this.color}${this.name}`
}
const cat = Animal.bind(null, "cat")
const cat = new Cat("white")
if (
  cat.say() === "I'm white cat" &&
  cat instanceof Cat &&
  cat instanceof Animal
) {
  console.log("sunccess")
}
```

## 24 请写出代码执⾏结果，并解释为什么

```javascript
function yideng() {
  console.log(1)
}
;(function () {
  if (false) {
    function yideng() {
      console.log(2)
    }
  }
  console.log(typeof yideng)
  yideng()
})()
```

## 25 数组里面有 10 万个数据，取第一个元素和第 10 万个元素的时间相差多少

## 26 说一下对于堆栈的理解？说一下栈和堆的区别，垃圾回收时栈和堆的区别

## 27 介绍 JS 全部数据类型，基本数据类型和引用数据类型的区别？用 typeOf 判断分别显示什么？Array 是 Object 类型吗？

## 28 原生实现 addClass,用多种方法

## 29 介绍宏任务和微任务？微任务和宏任务的区别？JavaScript 为什么要区分微任务和宏任务？

## 30 a 标签默认事件禁掉之后做了什么才实现了跳转?怎样用 css 实现一个弹幕的效果，动手实现一下？
