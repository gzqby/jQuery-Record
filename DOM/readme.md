# DOM
1. Attr: (该类型使用对象来表示一个DOM元素的属性)
2. Comment: (接口代表标签（markup）之间的文本符号（textual notations）。尽管它通常不会显示出来，但是在查看源码时可以看到它们。)
3. childNode(实验API)
```
// 将 ChildNode 其父节点的子节点
ChildNode.remove();
ChildNode.after();
ChildNode.before();
ChildNode.replaceWith();
```
4. CustomEvent: (事件是由程序创建的，可以有任意自定义功能的事件，此接口从父接口Event继承属性)
```
ele.addEventListener('cat', ()=> {console.log("event dispatch")})

const event = new CustomEvent('cat',{
  // 表示该事件能否冒泡
  bubbles: boolean,
  // 表示该事件能否取消
  cancelable: boolean
});

ele.dispatchEvent(event)
```
5. [Document](./document.md): 接口表示任何在浏览器中载入的网页，并作为网页内容的入口，也就是DOM 树
6. documentFragment: 最小文档对象 and parentNode和其属性方法一致
```
// property
documentFragment.fisrtElementChild
documentFragment.lastElementChild
documentFragment.children
documentFragment.childElementCount
// method
documentFragment.append()
documentFragment.prepend()
documentFragment.querySelector()
documentFragment.querySelector()
documentFragment.querySelectorAll()
documentFragment.querySelectorAll()
documentFragment.replaceChildren()
```
7. [Element](./Element.md): 是一个通用性非常强的基类，所有 Document 对象下的对象都继承自它。这个接口描述了所有相同种类的元素所普遍具有的方法和属性。一些接口继承自 Element 并且增加了一些额外功能的接口描述了具体的行为。
8. [event](./Event.md) 
9. eventTarget: 是一个 DOM 接口，由可以接收事件、并且可以创建侦听器的对象实现
10. HTMLCollection: HTML DOM 中的 HTMLCollection 是即时更新的（live）
11. MutationObserver: 接口提供了监视对DOM树所做更改的能力
12. [Node](./Node.md): 是一个接口，各种类型的 DOM API 对象会从这个接口继承.以下接口都从 Node 继承其方法和属性：
`Document, Element, Attr, CharacterData (which Text, Comment, and CDATASection inherit), ProcessingInstruction, DocumentFragment, DocumentType, Notation, Entity, EntityReference
在方法和属性不相关的特定情况下，这些接口可能返回 null`
13. NodeList: node.childNodes
```
NodeList.item()
NodeList.entries()
NodeList.forEach()
NodeList.keys()
NodeList.values()
```
14. URL
```
new URL("https://baidu.com?search=zigo")
URL {
  hash: "",
  host: "baidu.com",
  hostname: "baidu.com",
  href: "https://baidu.com/?search=zigo",
  origin: "https://baidu.com",
  password: "",
  pathname: "/",
  port: "",
  protocol: "https:",
  search: "?search=zigo",
  searchParams: URLSearchParams {},
  username: "",
  __proto__: URL
}
```
15. [window](./window.md)
16. HTMLDocument(HTMLDocument 是 DOM 的一个抽象接口，它提供了 XML 文档里没有出现的特殊属性和方法) - [HTMLElement](./HTMLElement.md)