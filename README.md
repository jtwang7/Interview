# 前端知识点汇总
# JavaScript
* 原始值和引用值类型及区别
  * [【JS 进阶】你真的掌握变量和类型了吗](https://juejin.cn/post/6844903854882947080)

* 判断数据类型typeof、instanceof、Object.prototype.toString.call()、constructor
  * [【JS 进阶】你真的掌握变量和类型了吗](https://juejin.cn/post/6844903854882947080)

* 类数组与数组的区别与转换
  * [JavaScript 类数组对象与 arguments](https://juejin.cn/post/6844903711022514184)
  * [类数组转化](https://juejin.cn/post/6844903976081555470#heading-78)

* 数组的常见API
  * [js 数组详细操作方法及解析合集](https://juejin.cn/post/6844903614918459406)

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
