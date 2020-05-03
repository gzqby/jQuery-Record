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
