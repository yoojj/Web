# Node

https://dom.spec.whatwg.org/#interface-node


```webidl
[Exposed=Window]
interface Node : EventTarget {
  const unsigned short ELEMENT_NODE = 1;
  const unsigned short ATTRIBUTE_NODE = 2;
  const unsigned short TEXT_NODE = 3;
  const unsigned short CDATA_SECTION_NODE = 4;
  const unsigned short ENTITY_REFERENCE_NODE = 5; // legacy
  const unsigned short ENTITY_NODE = 6; // legacy
  const unsigned short PROCESSING_INSTRUCTION_NODE = 7;
  const unsigned short COMMENT_NODE = 8;
  const unsigned short DOCUMENT_NODE = 9;
  const unsigned short DOCUMENT_TYPE_NODE = 10;
  const unsigned short DOCUMENT_FRAGMENT_NODE = 11;
  const unsigned short NOTATION_NODE = 12; // legacy
  readonly attribute unsigned short nodeType;
  readonly attribute DOMString nodeName;

  readonly attribute USVString baseURI;

  readonly attribute boolean isConnected;
  readonly attribute Document? ownerDocument;
  Node getRootNode(optional GetRootNodeOptions options = {});
  readonly attribute Node? parentNode;
  readonly attribute Element? parentElement;
  boolean hasChildNodes();
  [SameObject] readonly attribute NodeList childNodes;
  readonly attribute Node? firstChild;
  readonly attribute Node? lastChild;
  readonly attribute Node? previousSibling;
  readonly attribute Node? nextSibling;

  [CEReactions] attribute DOMString? nodeValue;
  [CEReactions] attribute DOMString? textContent;
  [CEReactions] undefined normalize();

  [CEReactions, NewObject] Node cloneNode(optional boolean deep = false);
  boolean isEqualNode(Node? otherNode);
  boolean isSameNode(Node? otherNode); // legacy alias of ===

  const unsigned short DOCUMENT_POSITION_DISCONNECTED = 0x01;
  const unsigned short DOCUMENT_POSITION_PRECEDING = 0x02;
  const unsigned short DOCUMENT_POSITION_FOLLOWING = 0x04;
  const unsigned short DOCUMENT_POSITION_CONTAINS = 0x08;
  const unsigned short DOCUMENT_POSITION_CONTAINED_BY = 0x10;
  const unsigned short DOCUMENT_POSITION_IMPLEMENTATION_SPECIFIC = 0x20;
  unsigned short compareDocumentPosition(Node other);
  boolean contains(Node? other);

  DOMString? lookupPrefix(DOMString? namespace);
  DOMString? lookupNamespaceURI(DOMString? prefix);
  boolean isDefaultNamespace(DOMString? namespace);

  [CEReactions] Node insertBefore(Node node, Node? child);
  [CEReactions] Node appendChild(Node node);
  [CEReactions] Node replaceChild(Node node, Node child);
  [CEReactions] Node removeChild(Node child);
};

dictionary GetRootNodeOptions {
  boolean composed = false;
};
```


속성 | 설명
---|---
nodeType    | 노드 타입을 숫자로 반환
nodeName    | 노드 타입을 문자로 반환  
baseURI     | 문서의 기본 url 반환
isConnected | 노드가 연결되었는지 여부 반환  
ownerDocument | 노드를 포함하는 문서?
parentNode  | 노드의 부모 노드
parentElement |
childNodes  | 노드의 자식 노드
firstChild  | 노드의 첫번째 자식 노드
lastChild   | 노드의 마지막 자식 노드
previousSibling | 노드의 형제 노드 중 바로 앞 노드
nextSibling | 노드의 형제 노드 중 바로 뒤 노드
nodeValue   |
textContent |


**getRootNode()**


**hasChildNodes()**


**normalize()**


**cloneNode()**   
: 해당 노드의 복제본 반환   

```js
var newNode = el.cloneNode();

// 자식 노드를 포함해 복제
var newNode = el.cloneNode(true);
```


**isEqualNode()**  
: 주어진 노드와 해당 노드가 같은 노드인지 여부 반환

```html
<div>true</div>
<div>false</div>
<div>true</div>

<script>
var div = document.getElementsByTagName('div');

div[0].isEqualNode(div[0]) === true
div[0].isEqualNode(div[1]) === false
div[0].isEqualNode(div[2]) === true
</script>
```


**isSameNode()**   
: 주어진 노드와 해당 노드가 동일한 노드인지 여부 반환

```html
<div id="div"></div>

<script>
var el1 = document.getElementById('div');
var el2 = document.getElementsByTagName('div')[0];

el1.isSameNode(el2) === true
</script>
```


**compareDocumentPosition()**

상태 | 값 |설명
---|---|---
DOCUMENT_POSITION_DISCONNECTED | 1 |
DOCUMENT_POSITION_PRECEDING  | 2 |
DOCUMENT_POSITION_FOLLOWING  | 4 |  
DOCUMENT_POSITION_CONTAINS   | 8 |
DOCUMENT_POSITION_CONTAINED_BY | 16 |
DOCUMENT_POSITION_IMPLEMENTATION_SPECIFIC | 32 |


**contains()**  
: 주어진 인자가 해당 노드의 하위 노드인지 여부 반환  

```js
var result = el.contains('node');
```


**lookupPrefix()**  
: 주어진 네임스페이스와 관련된 접두사 반환  

```js
var result = el.lookupPrefix('NS');
```


**lookupNamespaceURI()**   
: 주어진 접두사와 일치하는 네임스페이스 반환   

```js
var result = el.lookupNamespaceURI('prefix');
```


**isDefaultNamespace()**  
: 주어진 네임스페이스와 일치하는지 여부 반환   

```js
var result = el.isDefaultNamespace('NS');
```


**insertBefore()**  
: 주어진 노드를 레퍼런스 노드의 위치를 기준으로 삽입   

```js
parentNode.insertBefore('newNode', 'referenceNode');

// appendChild() 메소드와 동일  
parentNode.insertBefore('newNode', null);
```


**appendChild()**  
: 주어진 노드를 부모 노드의 마지막 자식으로 추가  

```js
parentNode.appendChild('newChildNode');
```


**replaceChild()**  
: 주어진 노드를 기존 노드와 바꿈

```js
parentNode.replaceChild('newChildNode', 'oldChildNode');
```


**removeChild()**   
: 주어진 노드를 부모 노드에서 제거하고 이를 반환   

```js
var childNode = parentNode.removeChild('childNode');
```



[top](#)
