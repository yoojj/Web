# Web Storage API
: 유저 에이전트에 키/값 형식의 데이터 저장을 위한 API   
: 데이터는 도메인이나 프로토콜에 따라 별도로 저장    
: 일반적으로 5MB 저장 크기를 지원 (브라우저에 따라 달라질 수 있음)  
: 스토리지 한도에 도달하면 LRU 정책에 따라 데이터를 삭제함   
: 브라우저 인스펙터를 통해 저장된 데이터를 확인하거나 수정할 수 있음


https://www.w3.org/TR/webstorage/   
https://html.spec.whatwg.org/multipage/webstorage.html


**세션 스토리지**   
: 하나의 창을 기준으로 독립적인 데이터 저장    
: 데이터는 창이 유지되는 동안만 사용 가능


**로컬 스토리지**   
: 하나의 브라우저를 기준으로 데이터 저장   
: 데이터는 영구적으로 사용 가능   



## API

**Storage**
- length
- key(index)
- getItem(key)
- setItem(key, value)
- removeItem(key)
- clear()


**WindowSessionStorage**
- sessionStorage : 세션 영역의 Storage 객체 반환  


**WindowLocalStorage**
- localStorage : 로컬 영역의 Storage 객체 반환  


**StorageEvent**
- constructor(DOMString, StorageEventInit)
- key
- oldValue
- newValue
- url
- storageArea


```js
localStorage.setItem('key', 'value');
localStorage.getItem('key');
localStorage.removeItem('key');


window.addEventListener('storage', (e) => {
    localStorage.getItem(e.key);
});
```



[top](#)
