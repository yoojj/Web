# Element

https://dom.spec.whatwg.org/#interface-element


```webidl[Exposed=Window]
interface Element : Node {
  readonly attribute DOMString? namespaceURI;
  readonly attribute DOMString? prefix;
  readonly attribute DOMString localName;
  readonly attribute DOMString tagName;

  [CEReactions] attribute DOMString id;
  [CEReactions] attribute DOMString className;
  [SameObject, PutForwards=value] readonly attribute DOMTokenList classList;
  [CEReactions, Unscopable] attribute DOMString slot;

  boolean hasAttributes();
  [SameObject] readonly attribute NamedNodeMap attributes;
  sequence<DOMString> getAttributeNames();
  DOMString? getAttribute(DOMString qualifiedName);
  DOMString? getAttributeNS(DOMString? namespace, DOMString localName);
  [CEReactions] undefined setAttribute(DOMString qualifiedName, DOMString value);
  [CEReactions] undefined setAttributeNS(DOMString? namespace, DOMString qualifiedName, DOMString value);
  [CEReactions] undefined removeAttribute(DOMString qualifiedName);
  [CEReactions] undefined removeAttributeNS(DOMString? namespace, DOMString localName);
  [CEReactions] boolean toggleAttribute(DOMString qualifiedName, optional boolean force);
  boolean hasAttribute(DOMString qualifiedName);
  boolean hasAttributeNS(DOMString? namespace, DOMString localName);

  Attr? getAttributeNode(DOMString qualifiedName);
  Attr? getAttributeNodeNS(DOMString? namespace, DOMString localName);
  [CEReactions] Attr? setAttributeNode(Attr attr);
  [CEReactions] Attr? setAttributeNodeNS(Attr attr);
  [CEReactions] Attr removeAttributeNode(Attr attr);

  ShadowRoot attachShadow(ShadowRootInit init);
  readonly attribute ShadowRoot? shadowRoot;

  Element? closest(DOMString selectors);
  boolean matches(DOMString selectors);

  HTMLCollection getElementsByTagName(DOMString qualifiedName);
  HTMLCollection getElementsByTagNameNS(DOMString? namespace, DOMString localName);
  HTMLCollection getElementsByClassName(DOMString classNames);

  [CEReactions] Element? insertAdjacentElement(DOMString where, Element element); // legacy
  undefined insertAdjacentText(DOMString where, DOMString data); // legacy
};

dictionary ShadowRootInit {
  required ShadowRootMode mode;
  boolean delegatesFocus = false;
};



/* CSSOM */
partial interface Element {
  DOMRectList getClientRects();
  [NewObject] DOMRect getBoundingClientRect();
  undefined scrollIntoView(optional (boolean or ScrollIntoViewOptions) arg = {});
  undefined scroll(optional ScrollToOptions options = {});
  undefined scroll(unrestricted double x, unrestricted double y);
  undefined scrollTo(optional ScrollToOptions options = {});
  undefined scrollTo(unrestricted double x, unrestricted double y);
  undefined scrollBy(optional ScrollToOptions options = {});
  undefined scrollBy(unrestricted double x, unrestricted double y);
  attribute unrestricted double scrollTop;
  attribute unrestricted double scrollLeft;
  readonly attribute long scrollWidth;
  readonly attribute long scrollHeight;
  readonly attribute long clientTop;
  readonly attribute long clientLeft;
  readonly attribute long clientWidth;
  readonly attribute long clientHeight;
};



/* Typed OM */
partial interface Element {
    [SameObject] StylePropertyMapReadOnly computedStyleMap();
};
```


속성 | 설명
---|---
namespaceURI |
prefix       |
localName    |
tagName      |
id           |
className    |
classList    |
slot         |
attributes   |
shadowRoot   |



**hasAttributes()**  


**getAttributeNames()**  


**getAttribute()**  
: 해당 요소에서 주어진 속성의 값 반환  

```js
var value = el.getAttribute('attributeName');
```


**setAttribute()**  
: 해당 요소에 속성과 값 지정  

```js
el.setAttribute('attributeName', 'value');
```


**removeAttribute()**  


**removeAttributeNS()**  


**toggleAttribute()**  


**hasAttribute()**  


**hasAttributeNS()**  


**getAttributeNode()**  


**setAttributeNode()**  


**removeAttributeNode()**  


**attachShadow()**  


**closest()**   


**matches()**   


**webkitMatchesSelector()**   


**getElementsByTagName()**    
: 해당 요소의 범위에서 주어진 태그명을 갖는 요소 목록 반환  

```js
var elements = el.getElementsByTagName('tag');
```


**getElementsByTagNameNS()**   
: 해당 요소의 범위에서 주어진 태그명과 네임스페이스가 일치하는 요소 목록 반환  


**getElementsByClassName()**   
: 해당 요소의 범위에서 주어진 클래스명을 갖는 요소 목록 반환   


**insertAdjacentElement()**   


**insertAdjacentText()**   



[top](#)
