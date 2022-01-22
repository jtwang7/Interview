# Redux 面试题
## 什么是Redux？
[官方文档：Redux 是什么?](http://cn.redux.js.org/tutorials/essentials/part-1-overview-concepts#redux-%E6%98%AF%E4%BB%80%E4%B9%88%EF%BC%9F)
```
Redux 是 JavaScript 应用的状态容器，提供可预测的状态管理。
Redux 官方解释：Redux 是一个使用叫做“action”的事件来管理和更新应用状态的模式和工具库 它以集中式Store（centralized store）的方式对整个应用中使用的状态进行集中管理，其规则确保状态只能以可预测的方式更新。
它基于 flux 模式而不是 React 的 MVC 模式，简化了 React 中单向的数据传输形式，将状态管理完全从 React 中抽象出来。
```

## Redux工作原理/流程？
[官方文档：Redux 数据流](http://cn.redux.js.org/tutorials/essentials/part-1-overview-concepts#redux-%E6%95%B0%E6%8D%AE%E6%B5%81)
```
redux 通过一个唯一的 store 来统一管理状态。
1. 在 store 创建时初始化状态，UI 组件订阅监听 store 的更新并首次渲染。
2. 当应用程序中发生某些事情时：
  2.1 UI组件通过 dispatch 派发一个 action
  2.2 store 调用 reducer，通过传入之前的 state 和当前的 action 来更新 state
  2.3 store 通知 UI state 发生了变化
3. UI 基于新 state 重新渲染
```

## react 组件如何与 redux 连接？
```
1. 类组件：mapStateToProps；mapDispatchToProps；
2. 函数组件：useSelector; useDispatch;
```