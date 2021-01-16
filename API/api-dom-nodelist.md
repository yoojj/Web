# NodeList

https://dom.spec.whatwg.org/#interface-nodelist


```webidl
[Exposed=Window]
interface NodeList {
  getter Node? item(unsigned long index);
  readonly attribute unsigned long length;
  iterable<Node>;
};
```


속성 | 설명
---|---
length | 노드 개수 반환  


**item()**   
: 주어진 인덱스에 위치하는 노드 반환


**iterable**  

```js
node.childNodes.forEach( () => {});
```



---
**Live Collection**        
: DOM 변경 사항을 실시간으로 컬렉션에 반영    


**Static Collection**     
: DOM 변경 사항을 컬렉션에 반영하지 않음   


**Live vs Static**  
- Node.childNodes 경우 Live NodeList를 반환    
- Document.querySelectorAll() 경우 Static NodeList를 반환    



[top](#)
