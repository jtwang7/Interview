# 前端面试题
## 目录
* <a href='#001'>前端性能优化方案</a>
* <a href='#002'>XSS (Cross Site Scripting) 跨站脚本攻击</a>


## 面试题及简答
### <div id='001'>前端性能优化方案</div>
```js
1. 减少 HTTP 请求数量
2. 使用 HTTP2:
   HTTP2 支持 TCP 连接的多路复用。
3. 服务器压缩: 
   压缩传输文件的大小，例如 gzip 压缩。
4. 合理利用浏览器缓存: 
   强缓存/协商缓存/localStorage/sessionStorage/ajax 缓存等。
5. js 相关:
   * js 文件异步加载
   * 使用节流和防抖，减少触发频率
   * 避免频繁操作 DOM
   * 按需加载
6. css 相关:
   * 避免使用 @import，使用 link 代替
   * 使用 transform 来实现动画效果 [提升至合成层]
   * 移除无用的 css 代码，减少 css 文件大小
   * 减少回流和重绘
7. 图片格式:
   * 合理使用图片格式
   * 图片懒加载
   * 使用雪碧图
```

### <div id='002'>XSS (Cross Site Scripting) 跨站脚本攻击</div>
```js

```



## 手撕题
### 包装一个高阶函数，模拟发送请求 ，只取最后一次的结果，前面的promise还没完成的话就取消。
```js
function wrap(fn) {
  // Your Code
}

let count = 0;
function sendRequest() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve(++count)
    })
  });
}
let newWrap = wrap(sendRequest);
newWrap().then(console.log)
newWrap().then(console.log)
newWrap().then(console.log) //输出3
```
```js
// 思想：用一个数组接收所有请求的Promise对象，但最终执行的时候只执行最后一个promise的回调
function wrap(fn) {
  let promises = []; // promise数组
  // 包装高阶函数：接收函数作为参数 或 返回一个函数
  return function () {
    let p = fn(); // 执行请求，获得promise
    promises.push(p); // 将promise推入数组
    // 根据题目返回一个Promise对象
    return new Promise((resolve, reject) => {
      // 遍历promise数组
      promises.forEach((item, idx) => {
        item.then((val) => {
          // 若是最后一个promise，则传递值
          if (idx === promises.length - 1) {
            resolve(val);
          }
        }).catch((err) => {
          reject(err); 
        })
      })
    })
  }
}
```