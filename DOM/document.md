## Property
1. document.body
2. document.characterSet 只读属性返回当前文档的字符编码
3. document.compatMode 指示文档是否以 quirks 怪异模式或 strict 严格模式呈现
4. document.doctype 即<!DOCTYPE html> h5或xhtml等
5. document.documentElement 即html dom元素
6. document.documentURI 当前文档路径
7. document.embeds 返回当前文档的embeds元素
8. document.fonts 返回值是文档的 FontFaceSet 接口。FontFaceSet 接口对 加载新字体、检查已加载字体的加载状态 来说非常有用。
9. document.forms 返回当前文档中的 <form>元素的一个集合
10. document.head
11. document.hidden
12. document.images
13. document.links
14. document.implementation 返回与当前文档相关联的 DOM 实现。
15. document.scripts
16. document.visibilityState
<!-- 继承自parentNode -->
17. document.firstElementChild
18. parentNode.childElementCount
19. parentNode.children
20. document.lastElementChild
<!-- HTML 文件的 document 接口继承自 HTMLdocument 接口 -->
21. document.cookie
22. document.defaultView
23. document.designMode
24. document.dir
25. document.domain
26. document.lastModified
27. document.location
28. document.readyState
29. document.referrer 返回来源页面的 URI。
30. document.title
31. document.URL
<!-- Document 接口混入（mixin）DocumentOrShadowRoot 包含的属性。请注意，这些属性目前仅有 Chrome 实现；其他浏览器仍在 Document 接口上直接实现它们 -->
32. document.activeElement
33. document.styleSheets
## Method
1. document.adoptNode(externalNode) 导入当前文档的新节点
2. document.createAttribute(name) 
3. document.createComment(data) 创建注释内容
4. Document.createDocumentFragment() jquery使用其做dom节点合并添加
5. document.createElement(tagName)
6. document.createElementNS(namespaceURI, qualifiedName[, options]) [有效命名空间](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElementNS#Valid_Namespace_URI's)
7. document.createEvent(type);
```
// 创建事件
var event = document.createEvent('Event');

// 定义事件名为'build'.
event.initEvent('build', true, true);

// 监听事件
elem.addEventListener('build', function (e) {
  // e.target matches elem
}, false);

// 触发对象可以是任何元素或其他事件目标
elem.dispatchEvent(event);
```
8. document.createNodeIterator(root[, whatToShow[, filter]]) 
9. document.createRange();
10. document.createTextNode(data)
11. document.getElementsByTagName()、getElementsByTagName(namaspace,name)、getElementsByClassName()、getElementsByName()
12. document.hasStorageAccess() 方法返回了一个Promise来判断该文档是否有访问第一方储存的权限
13. document.importNode(externalNode, deep) 将外部文档的一个节点拷贝一份,然后可以把这个拷贝的节点插入到当前文档中
14. document.getElementById(),querySelectorAll(selector),querySelector(selector) 主流的选择器
15. document.write(), close(), open()
16. document.hasFocus()