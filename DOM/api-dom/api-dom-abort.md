# AbortController

https://dom.spec.whatwg.org/#interface-abortcontroller

```webidl
[Exposed=(Window,Worker)]
interface AbortController {
  constructor();

  [SameObject] readonly attribute AbortSignal signal;

  undefined abort();
};
```


**signal**    
: AbortSignal 인터페이스 반환    


**abort()**   
: DOM 요청을 취소하고 AbortSignal의 aborted 속성을 중단으로 설정    



# AbortSignal

https://dom.spec.whatwg.org/#interface-AbortSignal


```webidl
[Exposed=(Window,Worker)]
interface AbortSignal : EventTarget {
  readonly attribute boolean aborted;

  attribute EventHandler onabort;
};
```


**aborted**   
: DOM 요청이 중단되면(AbortController가 중단 신호를 보냄) true를 반환    



[top](#)
