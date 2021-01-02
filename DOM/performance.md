# Performance
## attributes
### performance.navigation（操作相关）
- redirectCount: 该属性值为几，就说明了当前页面重定向了多少次；

- type

  |type|description|
  | ---- | ---- |
  |0|当前页面是通过点击链接，书签和表单提交，或者脚本操作，或者在url中直接输入地址;|
  |1|点击刷新页面按钮或者通过Location.reload()方法显示的页面|
  |2|页面通过历史记录和前进后退访问时；|
### performance.timing（延迟相关）
### performance.memory（js堆相关）
### performance.timeOrigin（性能检测开始时间）
### performance.onresourcetimingbufferfull（性能缓存区已满时回调）
## methods
- mark(name):根据给出 name 值，在浏览器的性能输入缓冲区中创建一个相关的时间戳
- performance.clearMarks():将给定的 mark 从浏览器的性能输入缓冲区中移除
- measure(name, startMark, endMark)
- clearMeasures():将给定的 measure 从浏览器的性能输入缓冲区中
- Performance.getEntries(PerformanceEntryFilterOptions)
```
PerformanceEntryFilterOptions{
  name： performance entry 的名字
  entryType：entry 类型. 合法的 entry 类型可以从 PerformanceEntry.entryType 方法获取
  initiatorType：初始化资源的类型，例如：xmlhttprequest 、 other 、 script
}
``` 
- getEntries()
- getEntriesByName(name, type)
> name：测量的名字,startMark：测量的开始标志名字（也可以是 PerformanceTiming 属性的名称,endMark：测量的结束标志名字（也可以是 PerformanceTiming 属性的名称）
- clearResourceTimings():从浏览器的性能数据缓冲区中移除所有 entryType 是 resource 的 performance entries
- setResourceTimingBufferSize(maxSize):设置浏览器应在其性能条目缓冲区中保存的最大性能条目对象数
- now():返回一个表示从性能测量时刻开始经过的毫秒数