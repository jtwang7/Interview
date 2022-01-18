# 前端知识点汇总
# JavaScript
* 原始值和引用值类型及区别
  * [【JS 进阶】你真的掌握变量和类型了吗](https://juejin.cn/post/6844903854882947080)

* 判断数据类型typeof、instanceof、Object.prototype.toString.call()、constructor
  * [【JS 进阶】你真的掌握变量和类型了吗](https://juejin.cn/post/6844903854882947080)

* 类数组与数组的区别与转换
  * [JavaScript 类数组对象与 arguments](https://juejin.cn/post/6844903711022514184)
  * [类数组转化](https://juejin.cn/post/6844903976081555470#heading-78)
```js
类数组对象定义：指可以通过索引属性访问元素并且拥有length属性的对象。
let arrLike = {
  0: 'name',
  1: 'age',
  2: 'job',
  length: 3
}
类数组对象与数组对象的联系与区别：
联系：类数组对象在访问、赋值、获取长度上的操作与数组是一致的。
区别：类数组对象不能直接使用数组的方法。
若希望类数组对象能够和数组一样使用数组的方法，可以通过 Function.call 或者 Function.apply 方法来间接调用，或者将类数组对象转为数组对象后，使用数组方法。

类数组对象转数组对象的四种方法，以 arguments 为例：
1. Array.prototype.splice.call(arguments) ：改变slice里面的this指向arguments,使得arguments可间接调用数组的方法(会改变原对象)
2. Array.prototype.slice.apply(arguments) ：改变slice里面的this指向arguments,使得arguments可间接调用数组的方法(不会改变原对象)
3. Array.from(arguments) ：将类数组或可迭代对象创建为数组
4. [...arguments] ：扩展类数组,再重新定义为数组
```

* 数组的常见API
  * [js 数组详细操作方法及解析合集](https://juejin.cn/post/6844903614918459406)
```js
数组创建方法(4种)：
1. 字面量方式：let a = [2, 4, 6]
2. Array()：let a = Array(); let b = Array(3); let c = Array(2,4,6); // a:[]; b:[,,]; c:[2,4,6]
3. Array.of()：let a = Array.of(3); let b = Array.of(2,4,6); // a:[3]; b:[2, 4, 6]
Array.of() 出现的目的是为了解决上述构造器因参数个数不同，导致的行为有差异的问题。
4. Array.from()：将类数组对象或可迭代对象转为真正的数组（不改变原对象，返回新的数组）。

改变原数组的方法(9种)：
ES5:
1. a.splice()：增删改
2. a.sort()：排序
3. a.pop()：删尾
4. a.shift()：删首
5. a.push()：增尾
6. a.unshift()：删首
7. a.reverse()：反序
ES6:
8. a.copyWithin()：复制
9. a.fill()：填充
对于改变原数组的数组方法，注意避免在循环遍历中改变原数组的选项，比如: 改变数组的长度，导致遍历的长度出现问题。

不改变原数组的方法(8种)：
ES5：
1. a.slice()：浅拷贝
2. a.join()：基于自定义分隔符转字符串
3. a.toLocateString()：转字符串，逗号分隔
4. a.toString()：转字符串，逗号分隔
5. a.concat()：拼接
6. a.indexOf()：查找元素，返回第一个匹配元素的下标
7. a.lastIndexOf()：查找元素，返回第一个匹配元素的下标
ES7：
8. a.includes()：查找元素是否存在，返回布尔值

数组遍历方法(12种)：
ES5：
1. a.forEach()：遍历数组，对每项均执行回调
* 无法中途退出循环，只能用return退出本次回调，进行下一次回调。
* 它总是返回 undefined值,即使你return了一个值。
2. a.every()：检测数组所有元素是否都符合判断条件
3. a.some()：检测数组是否存在某元素符合判断条件
4. a.filter()：过滤原始数组，返回新数组
5. a.map()：对数组内各项元素调用回调进行处理，返回新的数组
6. a.reduce()：为数组提供从左到右的累加器，返回最终合并结果
7. a.reduceRight()：从右到左累加
ES6：
8. a.find()：根据条件找到数组成员
9. a.findIndex()：根据条件找到数组成员位置索引
10. a.keys()：遍历键名，返回包含键名的 Array Iterator 对象
11. a.values()：遍历键值，返回包含键值的 Array Iterator 对象
12. a.entries()：遍历键值对，返回包含键值对数组的 Array Iterator 对象
数组遍历方法的通用规则：
1. 对于空数组是不会执行回调函数的
2. 对于已在迭代过程中删除的元素，或者空元素会跳过回调函数
3. 遍历次数再第一次循环前就会确定，再添加到数组中的元素不会被遍历。
4. 如果已经存在的值被改变，则传递给 callback 的值是遍历到他们那一刻的值。
```

* bind、call、apply的区别
  * [「干货」细说 call、apply 以及 bind 的区别和用法](https://juejin.cn/post/6844903768132157447)

* new 操作符
  * [my-issue: JS 基础篇 - new 操作符 ](https://github.com/jtwang7/JavaScript-Note/issues/50)

* new 和 Object.create() 的区别
  * [JS 基础篇 - new 和 Object.create() 的区别](https://github.com/jtwang7/JavaScript-Note/issues/52)

* this 指向判断
  * [my-issue: JS深入浅出 - 确定 this 对象指向](https://github.com/jtwang7/JavaScript-Note/issues/6)

* JS 原型/原型链/继承
  * 《JavaScript 高级程序设计》(第 4 版) (P220 - 248)

* prototype与__proto__的关系与区别
  * [my-issue: JS 基础篇 - prototype与__proto__的关系与区别](https://github.com/jtwang7/JavaScript-Note/issues/51)

* 作用域、作用域链、执行期上下文
  * [JS深入浅出 - 执行上下文 (Excution Context)](https://github.com/jtwang7/JavaScript-Note/issues/3)
  * [JS深入浅出 - 变量对象](https://github.com/jtwang7/JavaScript-Note/issues/4)
  * [JS深入浅出 - 作用域链](https://github.com/jtwang7/JavaScript-Note/issues/5)

* JS 闭包及其应用场景
  * [my-issue: JS深入浅出 - 闭包](https://github.com/jtwang7/JavaScript-Note/issues/7)

* DOM 及 DOM 扩展
  * 通读《JavaScript 高级程序设计》(第 4 版) (第 14 章 DOM；第 15 章 DOM 扩展；第 16 章 DOM2 和 DOM3) P401 - P489

* JS 中的垃圾回收机制和内存泄漏
  * [JavaScript中的垃圾回收和内存泄漏](https://juejin.cn/post/6844903833387155464)

* DOM 级别事件绑定
  * 《JavaScript 高级程序设计》(第 4 版) (事件处理程序 P493 - 498)
  * [my-issue: JS 事件篇 - 事件处理程序](https://github.com/jtwang7/JavaScript-Note/issues/39)

* BOM 的 location 对象
  * [浏览器Location 对象，URL 对象，URLSearchParams 对象简析](https://juejin.cn/post/6999077663587434533)
  * [my-issue: JS BOM 篇 - location 对象](https://github.com/jtwang7/JavaScript-Note/issues/44#issue-1020633051)

* JS 的四种函数调用方式
  * [JS 中的函数调用](https://juejin.cn/post/6844903496253177863#heading-11)

* 函数柯里化及其通用封装
  * [「前端进阶」彻底弄懂函数柯里化](https://juejin.cn/post/6844903882208837645)
  * [my-issue: CodeShredded - 函数柯里化](https://github.com/jtwang7/Code-Shredded/issues/17)

* Event-Loop 事件循环 & 宏任务与微任务
  * [my-issue: JS 基础篇 - 宏任务与微任务 & EventLoop事件循环](https://github.com/jtwang7/JavaScript-Note/issues/49)

* JS 事件流(冒泡/捕获)
  * 《JavaScript 高级程序设计》(第 4 版) (P490 - 492)
  * [my-issue: JS 事件篇 - 事件冒泡 & 捕获机制](https://github.com/jtwang7/JavaScript-Note/issues/38)

* JS 事件委托
  * 《JavaScript 高级程序设计》(第 4 版) (P540 - 542)

* 浏览器从输入URL到页面渲染的整个流程（涉及到计算机网络数据传输过程、浏览器解析渲染过程）
  * [浅谈 DNS](https://github.com/jtwang7/Internet-Note/issues/11)
  * [TCP 连接的三次握手与四次挥手](https://github.com/jtwang7/Internet-Note/issues/6)
  * [浏览器页面渲染机制](https://github.com/jtwang7/JavaScript-Note/issues/53)

* 浏览器的回流（Reflow）和重绘（Repaints）
  * [my-issue: JS深入浅出 - 浏览器的重绘(Repaint)与回流(Reflow)](https://github.com/jtwang7/JavaScript-Note/issues/2)

* 跨域、同源策略及跨域实现方式和原理
  * [my-issue: 跨域、同源策略及跨域实现方式和原理](https://github.com/jtwang7/JavaScript-Note/issues/54)

* setTimeout 计时为何会出现误差？requestAnimationFrame？
  * [JS深入浅出 - requestAnimationFrame](https://github.com/jtwang7/JavaScript-Note/issues/1)

# ES6
* let / const
  * [let 和 const 命令](https://es6.ruanyifeng.com/#docs/let)
  * [my-issue: let / const](https://github.com/jtwang7/JavaScript-Note/issues/41#issue-1019611778)

* 变量提升与暂时性死区
  * [my-issue: let / const](https://github.com/jtwang7/JavaScript-Note/issues/41#issue-1019611778)

* 箭头函数
  * [箭头函数](https://es6.ruanyifeng.com/#docs/function#%E7%AE%AD%E5%A4%B4%E5%87%BD%E6%95%B0)

* Reflect 对象
  * [Reflect](https://es6.ruanyifeng.com/#docs/reflect)
  * [my-issue: Reflect](https://github.com/jtwang7/JavaScript-Note/issues/40#issue-1018367911)

* Iterator & Iterable & for...of...

* Class 基本语法
  * [Class 的基本语法](https://es6.ruanyifeng.com/#docs/class)

* Class 继承
  * [Class 的继承](https://es6.ruanyifeng.com/#docs/class-extends)

* Generator 基本语法
  * [Generator 函数的语法](https://es6.ruanyifeng.com/#docs/generator)

* Generator 的异步应用
  * [Generator 函数的异步应用](https://es6.ruanyifeng.com/#docs/generator-async)

* async 函数
  * [async 函数](https://es6.ruanyifeng.com/#docs/async)
  * [my-issue: ES6 - async](https://github.com/jtwang7/JavaScript-Note/issues/48#issue-1020804084)

# CSS
* CSS权重及其引入方式
  * [css权重和超越!important](https://juejin.cn/post/6844903894313598989#heading-6) 

* CSS 绘制三角形
  * [my-issue: CSS 绘制三角形](https://github.com/jtwang7/CSS-Note/issues/12#issue-972392371)

* CSS 绘制菱形/梯形/平行四边形
  * [my-issue: CSS 绘制梯形 / 平行四边形 / 菱形](https://github.com/jtwang7/CSS-Note/issues/12#issuecomment-946334723)

* 元素水平垂直居中
  * [CSS-水平居中、垂直居中、水平垂直居中](https://segmentfault.com/a/1190000014116655)
  * [16种方法实现水平居中垂直居中](https://juejin.cn/post/6844903474879004680)

* display: none, visibility: hidden, opacity: 0 的区别
  * [display:none visibility:hidden opacity:0 区别](https://juejin.cn/post/6844904200401502215)


# 计算机网络
> 通读文章：
> * [从输入URL到页面加载的过程？如何由一道题完善自己的前端知识体系！](https://juejin.cn/post/6844903574535667719)
> * [字节跳动最爱考的前端面试题：计算机网络基础](https://juejin.cn/post/6939691851746279437)

* TCP 与 UDP 区别
  * [my-issue: TCP 与 UDP](https://github.com/jtwang7/Interview/issues/6#issue-1005372215)
  * [TCP和UDP比较](https://juejin.cn/post/6844903800336023560)

* TCP 报文结构
  * [my-issue: TCP 报文首部格式](https://github.com/jtwang7/Internet-Note/issues/10)

* TCP 三次握手 / 四次挥手
  * [my-issue: TCP 连接的三次握手与四次挥手](https://github.com/jtwang7/Internet-Note/issues/6)

* HTTP 的请求方法
  * [my-issue: HTTP 请求方法概览](https://github.com/jtwang7/Internet-Note/issues/7)

* XSS / CSRF 攻击及防御
  * [【面试篇】寒冬求职之你必须要懂的Web安全](https://juejin.cn/post/6844903842635579405)
  * [能不能说一说XSS攻击？](https://juejin.cn/post/6844904021308735502#heading-64)
  * [能不能说一说CSRF攻击？](https://juejin.cn/post/6844904021308735502#heading-74)

* localStorage、sessionStorage 与 Cookie 
  * [能不能说一说浏览器的本地存储？各自优劣如何？](https://juejin.cn/post/6844904021308735502#heading-13)
  * [深入了解浏览器存储--从cookie到WebStorage、IndexedDB](https://juejin.cn/post/6844903812092674061)

* Cookie, Session, Token, JWT
  * [傻傻分不清之 Cookie、Session、Token、JWT](https://juejin.cn/post/6844904034181070861#heading-22)

* GET 与 POST 的区别
  * [my-issue: get和post请求方式的区别](https://github.com/jtwang7/Internet-Note/issues/9)
  > * [get请求在浏览器回退时是无害的这句话要怎么理解](https://segmentfault.com/q/1010000014456539)
  > * [my-issue: post提交数据的编码格式？](https://github.com/jtwang7/Internet-Note/issues/8)

* HTTP 长连接/短连接
  * [http的长连接和短连接（史上最通俗！）](https://www.jianshu.com/p/3fc3646fad80)
  * [聊聊 TCP 长连接和心跳那些事](https://juejin.cn/post/6844903765674295309)
  * [my-issue: HTTP 长连接/短连接](https://github.com/jtwang7/Interview/issues/7#issue-1008194545)

* HTTP 长轮询/短轮询
  * [http的长连接和短连接（史上最通俗！）](https://www.jianshu.com/p/3fc3646fad80)

* ARP 协议
  * [图解ARP协议（一）](https://zhuanlan.zhihu.com/p/28771785)

* HTTPS与HTTP区别及实现方式
  * [my-issue: HTTPS ?](https://github.com/jtwang7/Internet-Note/issues/13)

* 基于 HTTP 的功能追加协议
  * [my-issue: 基于 HTTP 的功能追加协议](https://github.com/jtwang7/Internet-Note/issues/14)


# React
* Virtual DOM
  * [深度剖析：如何实现一个 Virtual DOM 算法](https://github.com/livoras/blog/issues/13)
  * [虚拟 DOM 到底是什么？](https://juejin.cn/post/6844903870229905422#heading-20)
  * [my-issue: Virtual DOM](https://github.com/jtwang7/React-Note/issues/31#issue-997094866)

* 生命周期
  * [React.Component](https://zh-hans.reactjs.org/docs/react-component.html#constructor)
  * [你真的了解 React 生命周期吗](https://juejin.cn/post/6844904021233238024#heading-2)

* Hooks 作用及原理
  > 首先推荐阅读 React 官方的 Hooks 文档, 了解 React Hook 的概念和设计动机

  * [Hook 简介](https://zh-hans.reactjs.org/docs/hooks-intro.html)
  * [Hook 概览](https://zh-hans.reactjs.org/docs/hooks-overview.html)
  * [Making Sense of React Hooks](https://medium.com/@dan_abramov/making-sense-of-react-hooks-fdbde8803889) 

  > 其次详细了解 useState, useEffect, useMemo, useCallback, useRef 等具体 React 内置 Hook 的使用细节

  * [Hook API 索引](https://zh-hans.reactjs.org/docs/hooks-reference.html#usestate)
  * [Hook 规则](https://zh-hans.reactjs.org/docs/hooks-rules.html)
  * [自定义 Hook](https://zh-hans.reactjs.org/docs/hooks-custom.html)

  > 最后，建议了解当前社区对一些常见 Hook 使用疑点的解答
  
  * [Hooks FAQ](https://zh-hans.reactjs.org/docs/hooks-faq.html)

* 受控组件与非受控组件
  * [my-issue: 受控组件 & 非受控组件](https://github.com/jtwang7/React-Note/issues/35#issue-1040890566)

* Flux架构模式（涉及MVC/MVVM、Flux）
  * [my-issue: 浅谈前端架构模式(MVC / MVP / MVVM / Flux)](https://github.com/jtwang7/React-Note/issues/33#issue-1040755482)

* 纯组件（Pure Component）与shouldComponentUpdate关系
  * [my-issue: 浅谈 PureComponent 和 shouldComponentUpdate 间的关系](https://github.com/jtwang7/React-Note/issues/34)


# Code Shredded
## 推荐文章
* [死磕 36 个 JS 手写题（搞懂后，提升真的大）](https://juejin.cn/post/6946022649768181774)

* 防抖与节流
  * [JavaScript专题之跟着underscore学防抖](https://github.com/mqyqingfeng/Blog/issues/22)
  * [JavaScript专题之跟着 underscore 学节流](https://github.com/mqyqingfeng/Blog/issues/26)
  * [my-issue: 简易版防抖](https://github.com/jtwang7/Code-Shredded/blob/master/%E9%98%B2%E6%8A%96%E5%92%8C%E8%8A%82%E6%B5%81/debounce_simple.js)
  * [my-issue: 升级版防抖](https://github.com/jtwang7/Code-Shredded/blob/master/%E9%98%B2%E6%8A%96%E5%92%8C%E8%8A%82%E6%B5%81/debounce.js)
  * [my-issue: 节流-非立即执行](https://github.com/jtwang7/Code-Shredded/blob/master/%E9%98%B2%E6%8A%96%E5%92%8C%E8%8A%82%E6%B5%81/throttle2_simple.js)
  * [my-issue: 节流-立即执行](https://github.com/jtwang7/Code-Shredded/blob/master/%E9%98%B2%E6%8A%96%E5%92%8C%E8%8A%82%E6%B5%81/throttle_simple.js)
  * [my-issue: 完整版节流](https://github.com/jtwang7/Code-Shredded/blob/master/%E9%98%B2%E6%8A%96%E5%92%8C%E8%8A%82%E6%B5%81/throttle.js)
  * [my-issue: 升级版节流](https://github.com/jtwang7/Code-Shredded/blob/master/%E9%98%B2%E6%8A%96%E5%92%8C%E8%8A%82%E6%B5%81/throttle_super.js)

* Ajax原生实现
  * [Promise 封装 原生 Ajax](https://juejin.cn/post/6868583734213115911)
  * [原生JS实现Ajax请求](https://zhuanlan.zhihu.com/p/64167474)
  * [my-issue: Ajax-Promise](https://github.com/jtwang7/Code-Shredded/blob/master/AJAX%E8%AF%B7%E6%B1%82/ajax-promise.js)
  * [my-issue: Ajax-Callback](https://github.com/jtwang7/Code-Shredded/blob/master/AJAX%E8%AF%B7%E6%B1%82/ajax-callback.js)

* async 实现原理(spawn 函数)
  * [async 函数的实现原理](https://es6.ruanyifeng.com/#docs/async#async-%E5%87%BD%E6%95%B0%E7%9A%84%E5%AE%9E%E7%8E%B0%E5%8E%9F%E7%90%86)
  * [my-issue: async](https://github.com/jtwang7/Code-Shredded/blob/master/Async/async.js)
  
* 继承实现
  * [my-issue: 构造函数继承](https://github.com/jtwang7/Code-Shredded/blob/master/%E7%BB%A7%E6%89%BF/%E6%9E%84%E9%80%A0%E5%87%BD%E6%95%B0%E7%BB%A7%E6%89%BF.js)
  * [my-issue: 原型链继承](https://github.com/jtwang7/Code-Shredded/blob/master/%E7%BB%A7%E6%89%BF/%E5%8E%9F%E5%9E%8B%E9%93%BE%E7%BB%A7%E6%89%BF.js)
  * [my-issue: 原型式继承](https://github.com/jtwang7/Code-Shredded/blob/master/%E7%BB%A7%E6%89%BF/%E5%8E%9F%E5%9E%8B%E5%BC%8F%E7%BB%A7%E6%89%BF.js)
  * [my-issue: 组合式继承](https://github.com/jtwang7/Code-Shredded/blob/master/%E7%BB%A7%E6%89%BF/%E7%BB%84%E5%90%88%E5%BC%8F%E7%BB%A7%E6%89%BF.js)
  * [my-issue: 寄生组合式继承](https://github.com/jtwang7/Code-Shredded/blob/master/%E7%BB%A7%E6%89%BF/%E5%AF%84%E7%94%9F%E7%BB%84%E5%90%88%E5%BC%8F%E7%BB%A7%E6%89%BF.js)

* 数组去重
  * [my-issue: CodeShredded - 数组去重](https://github.com/jtwang7/Code-Shredded/issues/3)

* 几种排序算法的实现及其复杂度比较
  * [my-issue: CodeShredded - 排序算法](https://github.com/jtwang7/Code-Shredded/issues/18)

* JSONP 跨域实现
  * [my-issue: JSONP](https://github.com/jtwang7/Code-Shredded/blob/master/JSONP/jsonp.js)

* 深拷贝的几种方法与比较
  * [my-issue: CodeShredded - 拷贝](https://github.com/jtwang7/Code-Shredded/issues/19)

* Iterator 遍历器/ Iterable 可迭代对象实现
  * [my-issue: CodeShredded - Iterator](https://github.com/jtwang7/Code-Shredded/blob/master/Iterator%26Iterable/Iterator.js)
  * [my-issue: CodeShredded - Iterable](https://github.com/jtwang7/Code-Shredded/blob/master/Iterator%26Iterable/Iterable.js)

* 解析 URL 参数为对象
  * [my-issue: CodeShredded - 解析 URL 参数为对象](https://github.com/jtwang7/Code-Shredded/issues/20)

* 模板字符串解析
  * [my-issue: CodeShredded - 模板字符串解析](https://github.com/jtwang7/Code-Shredded/issues/21)

* 图片懒加载
  * [my-issue: CodeShredded - 图片懒加载](https://github.com/jtwang7/Code-Shredded/issues/22)

* 函数柯里化
  * [my-issue: CodeShredded - 函数柯里化](https://github.com/jtwang7/Code-Shredded/issues/17)

* 实现函数原型方法：bind / call / apply
  * [my-issue: bind](https://github.com/jtwang7/Code-Shredded/blob/master/call%26apply%26bind/bind.js)
  * [my-issue: call](https://github.com/jtwang7/Code-Shredded/blob/master/call%26apply%26bind/call.js)
  * [my-issue: apply](https://github.com/jtwang7/Code-Shredded/blob/master/call%26apply%26bind/apply.js)

* 实现数组原型方法
  * [my-issue: forEach](https://github.com/jtwang7/Code-Shredded/blob/master/%E6%95%B0%E7%BB%84%E6%96%B9%E6%B3%95/forEach.js)
  * [my-issue: every](https://github.com/jtwang7/Code-Shredded/blob/master/%E6%95%B0%E7%BB%84%E6%96%B9%E6%B3%95/every.js)
  * [my-issue: some](https://github.com/jtwang7/Code-Shredded/blob/master/%E6%95%B0%E7%BB%84%E6%96%B9%E6%B3%95/some.js)
  * [my-issue: find](https://github.com/jtwang7/Code-Shredded/blob/master/%E6%95%B0%E7%BB%84%E6%96%B9%E6%B3%95/find.js)
  * [my-issue: findIndex](https://github.com/jtwang7/Code-Shredded/blob/master/%E6%95%B0%E7%BB%84%E6%96%B9%E6%B3%95/findIndex.js)
  * [my-issue: fill](https://github.com/jtwang7/Code-Shredded/blob/master/%E6%95%B0%E7%BB%84%E6%96%B9%E6%B3%95/fill.js)
  * [my-issue: filter](https://github.com/jtwang7/Code-Shredded/blob/master/%E6%95%B0%E7%BB%84%E6%96%B9%E6%B3%95/filter.js)
  * [my-issue: reduce](https://github.com/jtwang7/Code-Shredded/blob/master/%E6%95%B0%E7%BB%84%E6%96%B9%E6%B3%95/reduce.js)
  * [my-issue: map(for 实现)](https://github.com/jtwang7/Code-Shredded/blob/master/%E6%95%B0%E7%BB%84%E6%96%B9%E6%B3%95/for-map.js)
  * [my-issue: map(reduce 实现)](https://github.com/jtwang7/Code-Shredded/blob/master/%E6%95%B0%E7%BB%84%E6%96%B9%E6%B3%95/reduce-map.js)

* EventEmitter 发布订阅模式
  * [my-issue: EventEmitter](https://github.com/jtwang7/Code-Shredded/blob/master/%E5%8F%91%E5%B8%83%E8%AE%A2%E9%98%85%E6%A8%A1%E5%BC%8F/EventEmitter.js)