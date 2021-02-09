# HTMLCollection
: 순서대로 정렬된 요소 목록을 위한 인터페이스       
: 유사 배열이므로 배열처럼 사용 불가  
: live collection으로 DOM 변경 사항을 실시간 반영  

https://dom.spec.whatwg.org/#htmlcollection


```webidl
[Exposed=Window, LegacyUnenumerableNamedProperties]
interface HTMLCollection {
  readonly attribute unsigned long length;
  getter Element? item(unsigned long index);
  getter Element? namedItem(DOMString name);
};
```


**item()**  
: 주어진 인덱스에 위치하는 요소 반환

```js
var el = document.getElementsByTagName('tag').item(0);
```


**namedItem()**  
: 주어진 값과 id 속성 값이 일치하는 요소 반환

```js
// <tag id="val">
var el = document.getElementsByTagName('tag').namedItem('val');
```


**+ HTMLCollection to Array**
```js
var elements = document.getElementsByTagName('tag');

var arr = [].slice.call(elements);
var arr = Array.from(elements);
var arr = [...elements];
```



# HTMLFormControlsCollection

https://html.spec.whatwg.org/multipage/common-dom-interfaces.html#htmlformcontrolscollection


```webidl
[Exposed=Window]
interface HTMLFormControlsCollection : HTMLCollection {
  getter (RadioNodeList or Element)? namedItem(DOMString name);  
};

[Exposed=Window]
interface RadioNodeList : NodeList {
  attribute DOMString value;
};
```



# HTMLOptionsCollection

https://html.spec.whatwg.org/multipage/common-dom-interfaces.html#htmloptionscollection


```webidl
[Exposed=Window]
interface HTMLOptionsCollection : HTMLCollection {
  [CEReactions] attribute unsigned long length;
  [CEReactions] setter undefined (unsigned long index, HTMLOptionElement? option);
  [CEReactions] undefined add((HTMLOptionElement or HTMLOptGroupElement) element, optional (HTMLElement or long)? before = null);
  [CEReactions] undefined remove(long index);
  attribute long selectedIndex;
};
```



[top](#)
