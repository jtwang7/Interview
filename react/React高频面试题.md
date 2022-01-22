# React高频面试题
## React 是什么？
```
React 是一个轻量级的 javascript UI 库，用于构建高效、快速的用户界面。它遵循组件设计模式、声明式编程范式和函数式编程概念，使用虚拟DOM来有效地操作DOM，遵循从高阶组件到低阶组件的单向数据流。
```

## 什么是虚拟DOM？
[my-issue:React - Virtual DOM](https://github.com/jtwang7/React-Note/issues/31)
```css
虚拟DOM(VDOM)：是真实 DOM 在内存中的表示。UI的表示形式保存在内存中，并与实际的 DOM 同步。
本质就是一个普通的 JavaScript 对象，包含了 tag、props、children 三个属性。
react 中通过 h 函数将 html 代码转为 VDOM，然后通过 render 函数将 VDOM 渲染成真实 DOM。
优势：1. 跨平台；2. 提升性能
```

## 类组件和函数组件之间的区别？
```
1. 内部是否维护状态state: 类组件内部维护组件自身的 state 并有生命周期钩子等特性；函数组件是无状态组件，只接受 props，且内部没有生命周期等特性，React16.8 引入了 Hooks 解决了函数组件无法使用 React 特性的问题。
(Hook 是 React 16.8 的新增特性。它可以让你在不编写 class 的情况下使用 state 以及其他的 React 特性。)

2. 性能方面：函数组件的性能比类组件的性能要高，因为类组件使用的时候要实例化，而函数组件直接执行函数取返回结果即可。
```

## React 如何处理事件？
[「react进阶」一文吃透react事件系统原理](https://juejin.cn/post/6955636911214067720#heading-29)
```
三个阶段：
✅ 事件合成阶段
构建初始化React合成事件和原生事件的对应关系，合成事件和对应的事件处理插件关系。

✅ 事件绑定阶段
1. 在 react diff 阶段，若发现对应 fiber 的 props 是React合成事件，比如 onClick，会按照事件系统逻辑单独处理。
2. 根据React合成事件类型，找到对应的原生事件的类型(一个合成事件类型可能由多个原生事件类型共同组成，如onChange)。大部分事件都按照冒泡逻辑处理，少数事件会按照捕获逻辑处理(比如scroll事件)。
3. 调用 addTrappedEventListener 进行真正的事件绑定，绑定在 document (React v16)上，dispatchEvent 为统一的事件处理函数。
有一点值得注意: 只有上述那几个特殊事件比如 scorll,focus,blur等是在事件捕获阶段发生的，其他的都是在事件冒泡阶段发生的，无论是onClick还是onClickCapture都是发生在冒泡阶段。

✅ 事件触发阶段
执行统一的事件处理函数 dispatchEvent，执行包含以下步骤：
1. 首先进行的是批量更新 batchUpdate (对应 setState 的批量更新机制)；
2. 然后会执行事件对应的处理插件中的核心 extractEvents 函数；
3. 最后通过 runEventsInBatch 执行事件队列，如果发现阻止冒泡，那么break跳出循环，最后重置事件源，放回到事件池中，完成整个流程。
```
```
extractEvents 主要做的是：
1. 首先形成 React 事件独有的合成事件源对象，这个对象，保存了整个事件的信息。将作为参数传递给真正的事件处理函数 handerClick。
2. 然后声明事件执行队列 ，按照冒泡和捕获逻辑，从触发事件的位置(事件源)开始逐渐向上，查找 dom 元素类型 HostComponent 对应的 fiber ，收集上面的 React 合成事件，例如 onClick / onClickCapture ，对于冒泡阶段的事件(onClick)，将 push 到执行队列后面 ， 对于捕获阶段的事件(onClickCapture)，将 unShift到执行队列的前面。
[React 就是用这个队列，来模拟事件捕获->事件源->事件冒泡这一过程。]
3. 最后将事件执行队列，保存到 React 的合成事件源对象上。等待执行。
```


## state 和 props 的区别？
[my-issue: React - props vs state](https://github.com/jtwang7/React-Note/issues/1)
```
1. state 是在 React 组件内创建的，只能应用于该组件（类似于”在函数内创建的变量，受限于该函数的作用域“）; props 是由外部传入的，也可以在组件内赋予默认值。
2. state 是可修改的。而 props 是不能修改的。
state 必须通过 setState() 更新，setState() 为 state 提供了监听功能，只有通过 setState() 才能监听到 state 的变化并触发重新渲染，不能直接修改 state 值，这样是无法触发组件重渲染的。

3. state 与 props 在不同组件间的联系：state 可以接收 props，同样 state 也可以作为 props 传递给下一个子组件。
```

## 什么是 JSX?
```
JSX 是 JavaScript 的语法扩展 (JS + XML?)，个人理解 JSX 让 js 语法具备了以 html 形式书写的能力，但本质上仍是 js。
Babel 会把 JSX 转译成一个名为 React.createElement() 函数调用，将 html 标签转成 VDOM 表达。
```

## React 的生命周期？
[官方文档:组件的生命周期](https://zh-hans.reactjs.org/docs/react-component.html#the-component-lifecycle)
[生命周期图谱](https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/)
```
生命周期概念：react 组件从创建到销毁的过程。
生命周期函数：react 组件到达生命周期的某些特定阶段所执行的方法。
```
```
挂载/更新/销毁
挂载阶段：组件实例初始创建并插入到 DOM 中
1. constructor(): 组件挂载前最先执行 (初始化内部 state; 为事件处理函数绑定实例)。
2. static getDerivedStateFromProps(): 在调用 render 方法之前调用，并且在初始挂载及后续更新时都会被调用。它基于props返回一个对象来更新 state，如果返回 null 则不更新任何内容。简单理解就是在 render 前根据 props 预处理 state。
3. render(): 类组件唯一必须实现的方法，将组件渲染到真实DOM上。
4. componentDidMount(): 在组件挂载后（插入 DOM 树中）立即调用 (依赖DOM节点的初始化操作；网络请求；添加订阅)。

更新阶段：当组件的 props 或 state 发生变化时触发组件重渲染。
1. static getDerivedStateFromProps()
2. shouldComponentUpdate(): 组件重渲染的默认行为是 state 或 props 每次发生变化组件都会重新渲染，而 shouldComponentUpdate() 可以通过返回 Boolean 值来人为控制组件是否重渲染。
3. render()
4. getSnapshotBeforeUpdate(): 在最近一次渲染输出（提交到 DOM 节点）之前调用。它使得组件能在发生更改之前从 DOM 中捕获一些信息（例如，滚动位置）。此生命周期方法的任何返回值将作为参数传递给 componentDidUpdate()。
5. componentDidUpdate(): 在更新后会被立即调用。

卸载阶段：
1. componentWillUnmount(): 在组件卸载及销毁之前直接调用，执行一些清理操作(例如清除计时器，取消网络请求，清除订阅等)。

错误处理：
1. static getDerivedStateFromError()
2. componentDidCatch()
```
```
Render阶段/Pre-commit阶段/Commit阶段
Render阶段：生成真实DOM的阶段，纯净且不包含副作用。可能会被 React 暂停，中止或重新启动。
* constructor()
* static getDerivedStateFromProps()
* shouldComponentUpdate()
* render()

Pre-commit阶段：提交真实DOM之前的阶段，可以读取 DOM。
* getSnapshotBeforeUpdate()

Commit阶段：React接收并更新新的 DOM 和 refs 的阶段，可以使用 DOM，运行副作用，安排更新。
* componentDidMount()
* componentDidUpdate()
* componentWillUnmount()
```

## 什么是 React Hooks?
[my-issue:React - Hooks 概述](https://github.com/jtwang7/React-Note/issues/4)
```
Hook 是 React 16.8 的新增特性。它允许在不编写 class 的情况下使用 state 以及其他的 React 特性。
Hook 实现了状态逻辑的提取和重用。
```

## Hook 的使用规则?
[官方文档：Hook 规则](https://zh-hans.reactjs.org/docs/hooks-rules.html#gatsby-focus-wrapper)
```
1. 只在最顶层使用 Hook
不要在循环，条件或嵌套函数中调用 Hook， 确保总是在你的 React 函数的最顶层以及任何 return 之前调用他们。遵守这条规则，你就能确保 Hook 在每一次渲染中都按照同样的顺序被调用。这让 React 能够在多次的 useState 和 useEffect 调用之间保持 hook 状态的正确。

2. 只在 React 函数中调用 Hook
不要在普通的 JavaScript 函数中调用 Hook。你可以：
✅ 在 React 的函数组件中调用 Hook
✅ 在自定义 Hook 中调用其他 Hook

3. 以 use 为开头命名自定义 Hook，React 通过 use 来区分普通函数和 Hook 函数。
```

## 为什么 Hook 只能在顶层调用?
* [官方文档：说明](https://zh-hans.reactjs.org/docs/hooks-rules.html#explanation)
* [my-issue:React - Hooks (useState)](https://github.com/jtwang7/React-Note/issues/6)
```
在组件初始化（创建）时，React 会根据 hooks 的书写顺序存储对应的 hook，并构成一个链表结构，后续组件重新渲染时，会按照链表顺序遍历移动指针，并调用相应的 Hook。

React Hooks 对顺序性的要求，也约束了开发者书写 Hooks 的行为。我们只能将 Hooks 写在函数的最外层，不能写在 if ... else ... 或循环等语句中，确保 Hooks 的执行顺序与存储到链表结构中的顺序一致。
```


## 为什么类方法需要绑定到类实例？
```html
<button type="button" onClick={this.handleClick}>Click Me</button>
```
```
在 React 的类组件中，当我们把类方法作为事件处理的回调传递过去时(如上)，会丢失其隐式绑定的上下文，当事件被触发并且处理程序被调用时，this的值会回退到默认绑定，此时 this 在非严格模式下指向 window 或 global 对象。在严格模式下，this 指向 undefined。
```

## 受控组件和非受控组件区别是啥？
[my-issue:受控组件 & 非受控组件](https://github.com/jtwang7/React-Note/issues/35)
```
主要区别在于表单组件的状态是否是可控：
受控组件：状态由 react 的 state 状态维护，它的值保存在 this.state 中，并能使用 setState 将修改后的值同步到 state。
非受控组件：状态由元素自身内部维护，值保存在元素内部，数据的更新同步也是默认定义好并由内部机制完成的，外界无法对其做任何自定义的修改。外部使用非受控组件只能通过操纵其 DOM 节点来获取值。

从方法上分析：
表单数据状态受 React 的 state 控制，通过 setState 修改的就是受控组件，通过 DOM 控制，不受 state 控制的就是非受控组件。
```

## 如何提高 React 性能?
```
1. 在某些场合下尽量用 PureComponent 替代 Component，适当利用 shouldComponentUpdate 生命周期方法可以避免子组件不必要的渲染。 
2. 使用 create-react-app 来构建项目，这会创建整个项目结构，并进行大量优化。
3. 在显示列表或表格时始终使用 Keys，这会让 React 的更新速度更快
4. 按需加载模块。代码分离是将代码插入到单独的文件中，只加载模块或部分所需的文件。
```

## 如何在重新加载页面时保留数据？
```
将应用状态统一缓存到浏览器的 localstorage 中，每当重新加载应用程序时，我们从 localstorage 重新读取状态并加载。
```