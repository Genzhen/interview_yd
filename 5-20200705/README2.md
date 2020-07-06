# HTML&CSS：

## 浏览器内核

## 盒模型、flex 布局、两/三栏布局、水平/垂直居中；

## BFC、清除浮动；

## css3 动画、H5 新特性。

# JavaScript：

## 继承、原型链、this 指向、设计模式、call, apply, bind,；

## new 实现、防抖节流、let, var, const 区别、暂时性死区、event、loop；

## promise 使用及实现、promise 并行执行和顺序执行；

## async/await 的优缺点；

## 闭包、垃圾回收和内存泄漏、数组方法、数组乱序, 数组扁平化、事件委托、事件监听、事件模型

# Vue:

## vue 数据双向绑定原理；

## vue computed 原理、computed 和 watch 的区别；

## vue 编译器结构图、生命周期、vue 组件通信；

## mvvm 模式、mvc 模式理解；

## vue dom diff、vuex、vue-router

# 网络：

## HTTP1, HTTP2, HTTPS、常见的 http 状态码；

## 浏览从输入网址到回车发生了什么；

## 前端安全（CSRF、XSS）

## 前端跨域、浏览器缓存、cookie, session, token, localstorage, sessionstorage；

## TCP 连接(三次握手, 四次挥手)

# 性能相关

## 图片优化的方式

## 500 张图片，如何实现预加载优化

## 懒加载具体实现

## 减少 http 请求的方式

## webpack 如何配置大型项目

https://github.com/webfansplz/article

## 如何实现一个能强制中断死循环的方法?（实现 js 熔断机制）

死循环可以用 break 打断

```javascript
let idx=0
whild(1){
  idx++
  if(idx>10){
    break;
  }
}
```

#### 实现

`throw new Error()`和闭包来存储执行函数的次数，如果超过就跳出

```javascript
Function.prototype.fusing = function (option = { times: 100, timer: 1000 }) {
  let { times, timer } = option
  let start = new Data.getTime() // 获取当前时间戳
  const thisArgs = this
  return function () {
    thisArgs.apply(null, arguments)
    idx++
    let end = new Data.getTime() //获取执行时间
    if (idx >= times || end - start >= timer) {
      idx = 0
      start = null
      throw new Error("强制熔断")
    }
  }
}
```

调用的时候就可以自行使用函数

```javascript
funtion say(w){
  console.log(w)
}
var s = say.fusting()
while(1){
  s('测试')
}
```
