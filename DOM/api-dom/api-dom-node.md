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
isConnected | 노드가 컨텍스트 객체에 연결되었는지 여부 반환  
ownerDocument | 노드를 포함하는 최상위 문서 반환
parentNode  | 노드의 부모 노드 반환
parentElement | 노드의 부모 요소 반환
childNodes  | 노드의 모든 자식 노드 반환  
firstChild  | 노드의 첫번째 자식 노드 반환
lastChild   | 노드의 마지막 자식 노드 반환
previousSibling | 노드의 형제 노드 중 바로 앞에 위치한 노드 반환
nextSibling | 노드의 형제 노드 중 바로 뒤에 위치한 노드 반환  
nodeValue   | 노드의 값을 반환하거나 지정  
textContent | 노드의 텍스트 노드를 반환하거나 지정  


**nodeType & nodeName & nodeValue**

노드 타입 | nodeType | nodeName | nodeValue
---|---|---|---
Element | 1  | Element.tagName | null
Attr    | 2  | Attr.name | 속성 값
Text    | 3  | #text  | 내용
CDATASection | 4 | #cdata-section | 내용
ProcessingInstruction | 7 | ProcessingInstruction.target | 내용
Comment  | 8  | #comment | 내용
Document | 9  | #document | null
DocumentType  | 10 | DocumentType.name | null
DocumentFragment | 11 | #document-fragment | null


**nodeValue**   
: Attr, Text, CDATASection, ProcessingInstruction, Comment 경우 해당     

```html
<p>this is <b>tag</b></p>

<script>
var p = document.getElementsByTagName('p')[0];

(p.childNodes[0].nodeValue == 'this is ') == true
(p.childNodes[1].childNodes[0].nodeValue == 'tag') == true
</script>
```


**textContent**   
```html
<p>this is <b>tag</b></p>

<script>
var p = document.getElementsByTagName('p')[0];
(p.textContent == 'this is tag') == true
</script>
```


**getRootNode()**   
: 노드의 루트 노드 반환   

```js
var root = node.getRootNode();

// 옵션 설정
// https://dom.spec.whatwg.org/#concept-shadow-including-root
var root = node.getRootNode({ composed: true });
```


**hasChildNodes()**    
: 노드에 자식 노드가 있는지 여부 반환  


**normalize()**  
: 주어진 노드의 하위 노드를 정규화함  

- 태그 사이 공백 제거
- 속성과 값 사이 공백 제거
- 텍스트 노드의 줄바꿈이나 공백 제거
- 인접한 텍스트 노드를 단일 노드로 병합
- ...


**cloneNode()**   
: 노드의 복제본 반환   

```js
var newNode = node.cloneNode();

// 자식 노드를 포함해 복제
var newNode = node.cloneNode(true);
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
: 노드와 주어진 노드와의 관계를 비교하고 위치 값(비트 마스크) 반환   

상태 | 값 |설명
---|---|---
DOCUMENT_POSITION_DISCONNECTED | 1 | 노드가 같은 트리 내에 존재하지 않음
DOCUMENT_POSITION_PRECEDING  | 2 | 주어진 노드가 해당 노드 앞에 존재
DOCUMENT_POSITION_FOLLOWING  | 4 | 주어진 노드가 해당 노드 뒤에 존재
DOCUMENT_POSITION_CONTAINS   | 8 | 주어진 노드가 해당 노드를 포함함 (부모)
DOCUMENT_POSITION_CONTAINED_BY | 16 | 주어진 노드가 해당 노드에 포함됨 (자식)
DOCUMENT_POSITION_IMPLEMENTATION_SPECIFIC | 32 | 구현에 따라 다름

```html
<tag id="a">
    <tag id="b"></tag>
</tag>

<script>
var a = document.getElementById('a');
var b = document.getElementById('b');

// DOCUMENT_POSITION_CONTAINS + DOCUMENT_POSITION_PRECEDING
b.compareDocumentPosition(a) == 10

// DOCUMENT_POSITION_CONTAINED_BY + DOCUMENT_POSITION_FOLLOWING
a.compareDocumentPosition(b) == 20
</script>
```


**contains()**  
: 주어진 노드가 해당 노드의 하위 노드인지 여부 반환  

```js
var result = node.contains('node');
```


**lookupPrefix()**  
: 주어진 네임스페이스와 관련된 접두사 반환  

```js
var result = node.lookupPrefix('NS');
```


**lookupNamespaceURI()**   
: 주어진 접두사와 일치하는 네임스페이스 반환   

```js
var result = node.lookupNamespaceURI('prefix');
```


**isDefaultNamespace()**  
: 주어진 네임스페이스와 일치하는지 여부 반환   

```js
var result = node.isDefaultNamespace('NS');
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
