1. element.attributes 返回一个与该元素相关的所有属性集合
2. element.classList 返回classList
3. element.calssName
4. element.clientHeight 此属性会将获取的值四舍五入取整数。 如果你需要小数结果, 请使用 element.getBoundingClientRect().
```
clientLeft,clientTop,clientWidth
```
5. element.id
6. element.innerHTML
7. d.namespaceURI "http://www.w3.org/1999/xhtml"
8. element.localName
9. element.nextElementSibling element.previousElementSibling
10. element.outerHTML 基本返回自身与子代
11. element.prefix 
```
<x:div></div>
```
12. element.scrollTop scrollLeft scrollWidth scrollHeight
13. element.tagName
14. element.onfullscreenchange onfullscreenerror 
## Method
1. element.addEventListener removeEveontListener
```
addEventListener(type, {
  capture: Boolean, //捕获模式
  once: Boolean, //一次
  passive: Boolean, //表示 listener 永远不会调用 preventDefault()
}, useCapture: Boolean)
// 捕获先于冒泡
target.removeEventListener(type, listener[, options]);
```
2. element.attachShadow 创建shadowRoot
3. EventTarget.dispathchEvent
4. element.getAttribute 明确定义的属性  element.getAttributeNames 明确定义的属性名array  hasAttribute hasAttributeNS removeAttribute removeAttributeNS setAttribute setAttributeNS toggleAttribute
5. element.getBoundingClientRect element.getClientRects
6. element.getElementsByClassName element.getElementsByTagName element.getElementsByTagNameNS 听过tagname和namesapce获取  element.querySelector element.querySelectorAll
7. element.insertAdjacentElement(position, element) element.insertAdjacentHTML element.insertAdjacentText 插入到指定位置
8. element.matchs 选择器是否匹配到ele
9. element.remove 删除自身从dom中
10. element.requestFullscreen
11. element.requsetPointerLock
12. element.scroll(l,r) or ({}) scrollBy scrollTo
13. 接口的setPointerCapture() 方法用于将特定元素指定为未来指针事件的捕获目标