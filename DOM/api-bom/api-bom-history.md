# History

https://html.spec.whatwg.org/multipage/history.html#the-history-interface


```webidl
[Exposed=Window]
interface History {
  readonly attribute unsigned long length;
  attribute ScrollRestoration scrollRestoration;
  readonly attribute any state;
  undefined go(optional long delta = 0);
  undefined back();
  undefined forward();
  undefined pushState(any data, DOMString title, optional USVString? url = null);
  undefined replaceState(any data, DOMString title, optional USVString? url = null);
};

enum ScrollRestoration { "auto", "manual" };
```


속성 | 설명
---|---
length  | 방문 스택에 기록된 목록 수 반환
scrollRestoration  | 스크롤 위치 복원 여부를 지정하거나 반환   
state   | 현재 기록 상태 반환


```js
// 스크롤 위치 저장
history.scrollRestoration = 'manual';

// 스크롤 위치를 저장하지 않음
history.scrollRestoration = 'auto';
```


**history.go()**   
: 현재 페이지를 기준으로 전달된 값만큼 페이지 이동  

```js
history.go(-1) === history.back()
history.go(1) === history.forward()

history.go() === location.reload()
history.go(0) === location.reload()
```


**pushState()**    
: 방문 스택에 새로운 기록 추가   
: 페이지를 로드하지 않음  

```js
history.pushState({}, 'title', '/url');
```


**replaceState()**   
: 현재 기록 상태를 수정   

```js
history.replaceState({}, 'title', '/url');
```



[top](#)
