[Document](#document)     
[DOMImplementation](#domimplementation)   
[DocumentType](#documenttype)     
[DocumentFragment](#documentfragment)  



# Document

https://dom.spec.whatwg.org/#interface-document


```webidl
[Exposed=Window]
interface Document : Node {
  constructor();

  [SameObject] readonly attribute DOMImplementation implementation;
  readonly attribute USVString URL;
  readonly attribute USVString documentURI;
  readonly attribute DOMString compatMode;
  readonly attribute DOMString characterSet;
  readonly attribute DOMString charset; // legacy alias of .characterSet
  readonly attribute DOMString inputEncoding; // legacy alias of .characterSet
  readonly attribute DOMString contentType;

  readonly attribute DocumentType? doctype;
  readonly attribute Element? documentElement;
  HTMLCollection getElementsByTagName(DOMString qualifiedName);
  HTMLCollection getElementsByTagNameNS(DOMString? namespace, DOMString localName);
  HTMLCollection getElementsByClassName(DOMString classNames);

  [CEReactions, NewObject] Element createElement(DOMString localName,
    optional (DOMString or ElementCreationOptions) options = {});
  [CEReactions, NewObject] Element createElementNS(DOMString? namespace,
    DOMString qualifiedName, optional (DOMString or ElementCreationOptions) options = {});
  [NewObject] DocumentFragment createDocumentFragment();
  [NewObject] Text createTextNode(DOMString data);
  [NewObject] CDATASection createCDATASection(DOMString data);
  [NewObject] Comment createComment(DOMString data);
  [NewObject] ProcessingInstruction createProcessingInstruction(DOMString target, DOMString data);

  [CEReactions, NewObject] Node importNode(Node node, optional boolean deep = false);
  [CEReactions] Node adoptNode(Node node);

  [NewObject] Attr createAttribute(DOMString localName);
  [NewObject] Attr createAttributeNS(DOMString? namespace, DOMString qualifiedName);

  [NewObject] Event createEvent(DOMString interface); // legacy

  [NewObject] Range createRange();

  // NodeFilter.SHOW_ALL = 0xFFFFFFFF
  [NewObject] NodeIterator createNodeIterator(Node root,
    optional unsigned long whatToShow = 0xFFFFFFFF, optional NodeFilter? filter = null);
  [NewObject] TreeWalker createTreeWalker(Node root,
    optional unsigned long whatToShow = 0xFFFFFFFF, optional NodeFilter? filter = null);
};

dictionary ElementCreationOptions {
  DOMString is;
};



/* CSSSOM */
partial interface Document {
  [SameObject] readonly attribute StyleSheetList styleSheets;
};

partial interface Document {
  Element? elementFromPoint(double x, double y);
  sequence<Element> elementsFromPoint(double x, double y);
  CaretPosition? caretPositionFromPoint(double x, double y);
  readonly attribute Element? scrollingElement;
};
```


속성 | 설명
---|---
implementation | 문서의 DOMImplementation 객체 반환  
URL            | 문서의 url을 문자열로 반환  
documentURI    | 문서의 url을 문자열로 반환  
compatMode     | 렌더링 모드에 따른 문자열 반환   
characterSet   | 렌더링에서 사용하는 인코딩 반환  
contentType    | 렌더링되고 있는 MIME 타입 반환  
doctype        | 문서의 DTD 반환  
documentElement| 문서의 루트 요소 반환 (ex. html)


**compatMode**   
: 쿼크 모드면 BackCompat 문자열 반환
: 쿼크 모드가 아니면 CSS1Compat 문자열 반환


**getElementsByTagName()**    
: 주어진 태그명을 갖는 요소 목록 반환  

```js
// 모든 요소 반환
var elements = document.getElementsByTagName('*');
```


**getElementsByTagNameNS()**   
: 주어진 태그명과 네임스페이스가 일치하는 요소 목록 반환  


**getElementsByClassName()**   
: 주어진 클래스명을 갖는 요소 목록 반환   


**createElement()**  
: 주어진 태그명을 갖는 요소를 생성하고 이를 반환   

```js
var element = document.createElement('tag');
var customEl = document.createElement('custom-tag');

// <tag is="is-example">
document.createElement('tag', { is: 'is-example'});
```


**createElementNS()**   
: 네임 스페이스가 지정된 엘리먼트 생성  
: 네임 스페이스를 통해 SVG와 MathML 같은 XML 종류 식별   

```js
var html = document.createElementNS('http://www.w3.org/1999/xhtml', 'html');
var svg = document.createElementNS('http://www.w3.org/2000/svg', 'svg');
```


**createDocumentFragment()**   


**createTextNode()**   
: 텍스트 노드를 생성하고 이를 반환   


**createCDATASection()**   


**createComment()**   
: 주석 노드를 생성하고 이를 반환   


**createProcessingInstruction()**    

**importNode()**    

**adoptNode()**    


**createAttribute()**   
: 속성 노드를 생성하고 이를 반환   


**createAttributeNS()**    


**createRange()**
: 새 Range 객체 반환


**createNodeIterator()**   
: 새 NodeIterator 객체 반환


**createTreeWalker()**  
: 새 TreeWalker 객체 반환   



# DOMImplementation

```webidl
[Exposed=Window]
interface DOMImplementation {
  [NewObject] DocumentType createDocumentType(DOMString qualifiedName,
    DOMString publicId, DOMString systemId);
  [NewObject] XMLDocument createDocument(DOMString? namespace, [LegacyNullToEmptyString]
    DOMString qualifiedName, optional DocumentType? doctype = null);
  [NewObject] Document createHTMLDocument(optional DOMString title);

  boolean hasFeature(); // useless; always returns true
};
```



# DocumentType

https://dom.spec.whatwg.org/#interface-documenttype


```webidl
[Exposed=Window]
interface DocumentType : Node {
  readonly attribute DOMString name;
  readonly attribute DOMString publicId;
  readonly attribute DOMString systemId;
};
```



# DocumentFragment

https://dom.spec.whatwg.org/#interface-documentfragment

```webidl
[Exposed=Window]
interface DocumentFragment : Node {
  constructor();
};
```


[top](#)
