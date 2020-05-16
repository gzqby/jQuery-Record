# js编程思路与技巧
1.set函数中timeOut清除set值，能形成同步lock，只能同步get值。原理：  
```
setTimeout(()=>console.log(1), 100);
for(let i = 0; i<10000; i++) {
  console.log(2);
}
```
2.js代码生产环境会minify,具备一些特性，在没有process.env.NODE_ENV时可以用到  
```
function isMinified() {}
typeof isMinified.name === "string" && isMinified.name === "isMinified"
```
3.避免递归maximum call stack size exceeded：  
跳床函数，要递归的操作作为函数返回而不是直接执行，跳床函数再去执行。  
4.sleep:
```
async function sleep(inteval) {
  return new Promise((reslove)=>{
    setTimeOut(resplve, interval);
  })
}
```
5.宏任务微任务：
事件队列中的任务一个一个执行，但是需要高优先级得就需要微任务，它夹在当前宏任务末尾执行  
异步回调得两种形式，同步回调异步回调。异步回调就是能和setState一样得优化形式，多个连续得异步任务合一
创建微任务得形式：MutationObserver监控DOM监控到时得cb,Promise.resolve or .reject