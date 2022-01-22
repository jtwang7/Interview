# React高频面试题
## 什么是虚拟DOM？
[my-issue:React - Virtual DOM](https://github.com/jtwang7/React-Note/issues/31)
```css
虚拟DOM(VDOM)：是真实 DOM 在内存中的表示。UI的表示形式保存在内存中，并与实际的 DOM 同步。
本质就是一个普通的 JavaScript 对象，包含了 tag、props、children 三个属性。
react 中通过 h 函数将 html 代码转为 VDOM，然后通过 render 函数将 VDOM 渲染成真实 DOM。
优势：1. 跨平台；2. 提升性能
```