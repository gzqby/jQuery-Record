1.set函数中timeOut清除set值，能形成同步lock，只能同步get值。原理：  
```
setTimeout(()=>console.log(1), 100);
for(let i = 0; i<10000; i++) {
  console.log(2);
}
```
