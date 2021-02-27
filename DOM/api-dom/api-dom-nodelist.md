# NodeList

- Node.childNodes : Live NodeList 반환   
- Document.querySelectorAll() : Static NodeList 반환  


**Live vs Static**    
- Live Collection : DOM 변경 사항을 실시간으로 컬렉션에 반영   
- Static Collection : DOM 변경 사항을 컬렉션에 반영하지 않음    


https://dom.spec.whatwg.org/#interface-nodelist


```webidl
[Exposed=Window]
interface NodeList {
  getter Node? item(unsigned long index);
  readonly attribute unsigned long length;
  iterable<Node>;
};
```


**length**   
: 노드 개수 반환  

```js
var tag = document.getElementsByTagName('tag')[0];
var nodeList = tag.childNodes;
nodeList.length;
```


**item()**   
: 주어진 인덱스에 위치하는 노드 반환



[top](#)
