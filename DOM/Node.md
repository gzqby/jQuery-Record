## Attributes
1. node.baseURI
2. node.childNodes 包括text等全部的子节点
3. node.firstChild node.lastChild node.nextSibling(下一个) node.previousSibling node.parentNode node.parentElement(document.documentElement的parentNode是document，而parentElement是null)
4. node.isConnected 返回一个布尔值用来检测该节点是否已连接(直接或者间接)到一个上下文对象上,即装载
5. node.name
6. node.nodeType  
```
Name	                          Value
ELEMENT_NODE	                    1
TEXT_NODE	                        3
CDATA_SECTION_NODE	              4
PROCESSING_INSTRUCTION_NODE	      7
COMMENT_NODE	                    8
DOCUMENT_NODE	                    9
DOCUMENT_TYPE_NODE	              10
DOCUMENT_FRAGMENT_NODE	          11
<!-- Deprecated Api should no longer be used, but will probably still work -->
ATTRIBUTE_NODE 	                  2
ENTITY_REFERENCE_NODE 	          5
ENTITY_NODE 	                    6
NOTATION_NODE 	                  12
```
7. node.nodeValue 
```
Node	Value of nodeValue
CDATASection	CDATA的文本内容
Comment	注释的文本内容
Document	null
DocumentFragment	null
DocumentType	null
Element	null
NamedNodeMap	null
EntityReference	null
Notation	null
ProcessingInstruction	整个标签的文本内容
Text	文本节点的内容
```
8. node.ownerDocument
9. node.textContent
## Methods
1. node.appendChild(othernode) node.insertBefore(othernode) node.removeChild(childNode) node.replaceChild(oldChildNode, newChildNode)
2. node.cloneNode
3. node.compareDocumentPosition( otherNode )
```
常量名	十进制值	含义
DOCUMENT_POSITION_DISCONNECTED	1	不在同一文档中
DOCUMENT_POSITION_PRECEDING	2	otherNode在node之前
DOCUMENT_POSITION_FOLLOWING	4	otherNode在node之后
DOCUMENT_POSITION_CONTAINS	8	otherNode包含node
DOCUMENT_POSITION_CONTAINED_BY	16	otherNode被node包含
DOCUMENT_POSITION_IMPLEMENTATION_SPECIFIC	32	待定
```
4. node.contains(otherNode) 是否为该节点的后代节点
5. node.getRootNode(): 获取root节点
6. node.hasChildNodes(): 是否包含子节点
7. node.isDefaultNamespace(URI)
8. node.isEqualNode(othernode): 当两个 node 节点为相同类型的节点且定义的数据点匹配时（即属性和属性值相同，节点值相同）返回 true
9. node.isSameNode(othernode): 对比引用是否相同
10. node.normalize(): 对该元素下的所有文本子节点进行整理，合并相邻的文本节点并清除空文本节点。
11. 