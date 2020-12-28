# Web Storage API
: 유저 에이전트에 키/값 형식으로 데이터를 저장하기 위한 API   
: 데이터는 도메인이나 프로토콜에 따라 별도로 저장    
: 일반적으로 5MB 저장 크기를 지원 (브라우저에 따라 달라질 수 있음)  
: 스토리지 한도에 도달하면 LRU 정책에 따라 데이터를 삭제함   
: 브라우저 인스펙터를 통해 저장된 데이터를 확인하거나 수정할 수 있음


https://www.w3.org/TR/webstorage/   
https://html.spec.whatwg.org/multipage/webstorage.html


**api**
- [Storage](#storage)
- [StorageEvent](#storageevent)


ex.
```js
localStorage.setItem('key', 'value');
localStorage.getItem('key');
localStorage.removeItem('key');


window.addEventListener('storage', (e) => {
    localStorage.getItem(e.key);
});
```



## Storage

```webidl
[Exposed=Window]
interface Storage {
  readonly attribute unsigned long length;
  DOMString? key(unsigned long index);
  getter DOMString? getItem(DOMString key);
  setter undefined setItem(DOMString key, DOMString value);
  deleter undefined removeItem(DOMString key);
  undefined clear();
};


interface mixin WindowSessionStorage {
  readonly attribute Storage sessionStorage;
};

Window includes WindowSessionStorage;


interface mixin WindowLocalStorage {
  readonly attribute Storage localStorage;
};

Window includes WindowLocalStorage;
```


**세션 스토리지**   
: 하나의 창을 기준으로 독립적인 데이터 저장    
: 창을 기준으로 데이터 접근    
: 데이터는 창이 유지되는 동안만 사용 가능


**로컬 스토리지**   
: 하나의 브라우저를 기준으로 데이터 저장   
: 도메인을 기준으로 데이터 접근  
: 데이터는 영구적으로 사용 가능  



## StorageEvent**

```webidl
[Exposed=Window]
interface StorageEvent : Event {
  constructor(DOMString type, optional StorageEventInit eventInitDict = {});

  readonly attribute DOMString? key;
  readonly attribute DOMString? oldValue;
  readonly attribute DOMString? newValue;
  readonly attribute USVString url;
  readonly attribute Storage? storageArea;

  undefined initStorageEvent(DOMString type,
    optional boolean bubbles = false, optional boolean cancelable = false,
    optional DOMString? key = null, optional DOMString? oldValue = null,
    optional DOMString? newValue = null, optional USVString url = "",
    optional Storage? storageArea = null);
};

dictionary StorageEventInit : EventInit {
  DOMString? key = null;
  DOMString? oldValue = null;
  DOMString? newValue = null;
  USVString url = "";
  Storage? storageArea = null;
};
```



[top](#)
