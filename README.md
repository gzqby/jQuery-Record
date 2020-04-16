# jQuery-Record
jQuery.key 82,jQuery.fn.key 141
1.DomEval：script能通过text传递code给浏览器，之前没留意过的东西。  
```
var script = document.createElement("script");
script.text = "console.log(document.querySelector('#root'));document.querySelector('#root').innerHTML='hello wolrd'";
document.head.appendChild(script).parentNode.removeChild(script);
```
2.判断对象为空的一种：
```
for (name in obj) {
  return false;
}
```
3.plainObject
```
if ( !obj || toString.call( obj ) !== "[object Object]" ) {
  return false;
}
proto = getProto( obj );
if ( !proto ) {
  return true;
}

Ctor = hasOwn.call( proto, "constructor" ) && proto.constructor;
return typeof Ctor === "function" && fnToString.call( Ctor ) === ObjectFunctionString;
```
4.jQuery的arrayLike:  
```
array
||
{
  length: 1,
  0: "any"
}
```
5.nodeType:
```
Node.ELEMENT_NODE	1	一个 元素 节点，例如 <p> 和 <div>。
Node.TEXT_NODE	3	Element 或者 Attr 中实际的  文字
Node.CDATA_SECTION_NODE	4	一个 CDATASection，例如 <!CDATA[[ … ]]>。
Node.PROCESSING_INSTRUCTION_NODE	7	一个用于XML文档的 ProcessingInstruction ，例如 <?xml-stylesheet ... ?> 声明。
Node.COMMENT_NODE	8	一个 Comment 节点。
Node.DOCUMENT_NODE	9	一个 Document 节点。
Node.DOCUMENT_TYPE_NODE	10	描述文档类型的 DocumentType 节点。例如 <!DOCTYPE html>  就是用于 HTML5 的。
Node.DOCUMENT_FRAGMENT_NODE	11	一个 DocumentFragment 节点

3,4 nodeValue获取文本
1,9,11 textContent获取文本
也可以用nodeType判断是否是一个node
```
6.js做数组参数处理要注意string，而TS能屏蔽这种问题  
7.回调函数bind this，形成当前item作为this  
8.只能进出的简单栈
```
pushStack: function( elems ) {
  // Build a new jQuery matched element set
  var ret = jQuery.merge( this.constructor(), elems );

  // Add the old object onto the stack (as a reference)
  ret.prevObject = this;

  // Return the newly-formed element set
  return ret;
},
```
9.巧妙利用文件加载即执行部分  
10.document.activeElement可判断当前元素是否是active;  
11.ResizeObserver构造器创新一个新的  ResizeObserver 对象，用于接收 Element内容区域的改变 或 SVGElement 的边界框改变改变。  
```
a = new ResizeObserver((ResizeObserverEntries)=>{})
a.observe(element);
当element变化时callback触发
```
12.dom无中生有求解法，很多需要有特定dom元素才能取得得值，可以把dom隐藏式的添加，计算后缓存再remove。  
-- 网页可见区域宽： document.body.clientWidth （可变）  
-- 网页可见区域高： document.body.clientHeight （可变）  
-- 网页可见区域宽： document.body.offsetWidth (包括边线的宽)  
-- 网页可见区域高： document.body.offsetHeight (包括边线的高)  
-- 网页正文全文宽： document.body.scrollWidth  
-- 网页正文全文高： document.body.scrollHeight  
-- 网页被卷去的高： document.body.scrollTop  
-- 网页被卷去的左： document.body.scrollLeft  
-- 元素的实际高度：document.getElementById(“div”).offsetHeight  
-- 元素的实际宽度：document.getElementById(“div”).offsetWidth  
-- 元素的实际距离左边界的距离：document.getElementById(“div”).offsetLeft  
-- 元素的实际距离上边界的距离：document.getElementById(“div”).offsetTop  
--- scrollWidth：对象的实际内容的宽度，不包边线宽度，会随对象中内容超过可视区后而变大。  
--- clientWidth：对象内容的可视区的宽度，不包滚动条等边线，会随对象显示大小的变化而改变。  
--- offsetWidth：对象整体的实际宽度，包滚动条等边线，会随对象显示大小的变化而改变  
-- window.screen.availHeight：声明了显示浏览器的屏幕的可用高度， 固定值，不包含任务栏  
-- window.screen.availWidth): 浏览器的屏幕的宽度=width 1280 固定值  
-- window.screen.height: 浏览器屏幕实际高  
-- window.screen.width: 浏览器屏幕实际宽  
-- window.pageYOffset : 浏览器滚动条的上偏移  
-- window.pageXOffset) :浏览器滚动条的左偏移  
说明：  
（1）pageXOffset 设置或返回当前页面相对于窗口显示区左上角的 X 位置。pageYOffset 设置或返回当前页面相对于窗口显示区左上角的 Y 位置。
（2） pageXOffset 和 pageYOffset 属性相等于 scrollX 和 scrollY 属性。
（3）这些属性是只读的。
-- window.innerWidth：浏览器可视区域的高  
-- window.innerHeight ：浏览器可视区域的宽
-- Element.getBoundingClientRect() 返回元素大小及相对于视口的位置