## 动手实现一个 repeat 方法

function repeat(func, times, wait) {
// TODO
}
const repeatFunc = repeat(alert, 4, 3000);
// 调用这个 repeatFunc ("hellworld")，会 alert4 次 helloworld, 每次间隔 3 秒

## 项目中如何处理安全问题

## 整个前端性能提升大致分几类？如何加快页面渲染速度，都有哪些方式？动画性能如何检测

## 是否了解 docker，介绍一下

## 谈下淘宝和京东页面的实现？如何监控 MySql、Redis 性能

## 使用 typescript 的装饰器能否实现函数调用前出现加载动画，调用后关闭，如果能，这个加载动画的控制代码是放在哪种装饰器上呢

## 如何实现一个 mvvm 模型?介绍 MVP 怎么组织?

## 一个 dom 必须要操作几百次，该如何解决，如何优化？

## 请实现一个 cacheRequest 方法，保证发出多次同一个 ajax 请求时都能拿到数据，而实际上只发出一次请求

## scrollview 如何进行又能优化(例如 page=100 时，往上滚动)

## 页面埋点怎么实现

## 判断一个变量的类型，写个方法用 Object.prototype.toString 判断传入数据的类型？Object.prototype.toString.call(Symbol) 返回什么？

## gitlab 分支管理，线上如果发生 bug 怎么解决？git pull -rebase 和 git pull 的区别是什么？

## RN、Weex、Dart 的优缺点

## 前端和后端怎么联调?Access-Control-Allow-Origin 在服务端哪里配置

## if([] == 0), [1,2] == "1,2", if([]), [] == 0 具体是怎么对比的

## 以下 axios 的特点正确的有哪些？(多选题) 详细介绍下 axios

A.axios 可以跨平台，支持 promise 的所有 API
B.可以拦截请求和响应
C.可以转换请求数据和响应数据，并对响应回来的内容自动转换为 json 类型的数据
D.安全性更高，客户端支持防御 XSRF

## 说下 offsetWith 和 clientWidth、offsetHeight 和 clientHeight 的区别，说说 offsetTop，offsetLeft，scrollWidth、scrollHeight 属性都是干啥的

## 用原生 js 实现自定义事件

## 请写一个函数，输出出多级嵌套结构的 Object 的所有 key 值

var obj = {
a: "12",
b: "23",
first: {
c: "34",
d: "45",
second: { 3: "56", f: "67", three: { g: "78", h: "89", i: "90" } },
},
};
// => [a,b,c,d,e,f,g,h,i]

## 实现一个功能，发送请求 5s 时间后，如果没有数据返回，中断请求,提示错误

## 简单封装一个异步 fecth，使用 async await 的方式来使用

## 给定起止日期，返回中间的所有月份

// 输入两个字符串 2018-08 2018-12
// 输出他们中间的月份 [2018-10, 2018-11]

## switch case，case 具体是怎么比较的，哪些情况下会走到 default？说下 typeof()各种类型的返回值？instanceof 呢？

## 要求用不同方式对 A 进行改造实现 A.name 发生变化时立即执行 A.getName

/_
已知对象 A = {name: 'sfd', getName: function(){console.log(this.name)}},
现要求用不同的方式对 A 进行改造实现 A.name 发生变化时立即执行.getName
_/

## 实现 bind 方法，不能使用 call、apply、bind； 手写实现 call； 手写实现 apply

## 介绍下 JavaScript 中的设计模式？平时都用到了哪些设计模式

## 实现以下代码

function add() {
// your code
}
function one() {
// your code
}
function two() {
// your code
}
console.log(add(one(two()))); //3
console.log(add(two(one()))); //3

## reduce 函数的功能，如何实现的，动手实现一下

## 分别对以下数组进行去重，1:[1,'1',2,'2',3]，2:[1,[1,2,3['1','2','3'],4],5,6]

## 已知函数 A，要求构造 1 个函数 B 继承 A

function A(name) {
this.name = name;
}
A.prototype.getName = function () {
console.log(this.name);
};

## 实现一个函数将中文数字转成数字

## Promise 链式调用如何实现？genertor 的实现原理

## 如何把真实 dom 转变为虚拟 dom，代码实现一下

## 修改以下代码，使得最后一行代码能够输出数字 0-9（最好能给多种答案）

var arrys = [];
for (var i = 0; i < 10; i++) {
arrys.push(function () {
return i;
});
}
arrys.forEach(function (fn) {
console.log(fn());
}); //本行不能修改

## 原生 JavaScript 获取 ul 中的第二个 li 里边的 p 标签的内容，尝试多种方式

## 用 Promise 封装一个 ajax？ Promise 和 setTimeout 的区别

## 手写 EventEmitter 实现？ addEventListener 在 removeListener 会不会造成内存泄漏

## 如何做工程上的优化？如果有一个项目，随着业务的增长越来越大，怎么办，如何来进行一个拆分或者处理

## 数组截取插入 splice，push 返回值，数组的栈方法、队列方法、排序方法、操作方法、迭代方法说一下？判断是否是数组的方法都有哪些？

## 介绍 service worker，并说下对 service worker 的理解?

## 小程序里面打开页面最多多少，生命周期、常用的 api 列举几个？
