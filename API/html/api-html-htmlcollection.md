# HTMLCollection
: 순서대로 정렬된 요소 모음   
: 유사 배열이므로 배열처럼 사용 불가  

https://dom.spec.whatwg.org/#htmlcollection


```webidl
[Exposed=Window, LegacyUnenumerableNamedProperties]
interface HTMLCollection {
  readonly attribute unsigned long length;
  getter Element? item(unsigned long index);
  getter Element? namedItem(DOMString name);
};
```


속성 | 설명
---|---
length | 요소 개수 반환


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


**+ HTMLCollection to array**
```js
var elements = document.getElementsByTagName('tag');

var arr = [].slice.call(elements);
var arr = Array.from(elements);
var arr = [...elements];
```



[top](#)
