# Event

https://dom.spec.whatwg.org/#interface-event


```webidl
[Exposed=(Window,Worker,AudioWorklet)]
interface Event {
  constructor(DOMString type, optional EventInit eventInitDict = {});

  readonly attribute DOMString type;
  readonly attribute EventTarget? target;
  readonly attribute EventTarget? srcElement; // legacy
  readonly attribute EventTarget? currentTarget;
  sequence<EventTarget> composedPath();

  const unsigned short NONE = 0;
  const unsigned short CAPTURING_PHASE = 1;
  const unsigned short AT_TARGET = 2;
  const unsigned short BUBBLING_PHASE = 3;
  readonly attribute unsigned short eventPhase;

  undefined stopPropagation();
            attribute boolean cancelBubble; // legacy
  undefined stopImmediatePropagation();

  readonly attribute boolean bubbles;
  readonly attribute boolean cancelable;
           attribute boolean returnValue;  // legacy
  undefined preventDefault();
  readonly attribute boolean defaultPrevented;
  readonly attribute boolean composed;

  [LegacyUnforgeable] readonly attribute boolean isTrusted;
  readonly attribute DOMHighResTimeStamp timeStamp;

  undefined initEvent(DOMString type, optional boolean bubbles = false,
    optional boolean cancelable = false); // legacy
};

dictionary EventInit {
  boolean bubbles = false;
  boolean cancelable = false;
  boolean composed = false;
};
```


속성 | 설명
---|---
type       | 이벤트 타입을 문자열로 반환  
target     | 이벤트가 전달되는 객체 반환  
currentTarget |
eventPhase | 이벤트 흐름 단계 반환
bubbles    | 이벤트 버블링 방식 사용 여부 반환
cancelable | 이벤트 취소 가능 여부 반환  
defaultPrevented |
composed   |
isTrusted  | 유저 에이전트에 의해 이벤트가 전달되면 참 반환
timeStamp  | 이벤트 타임 스탬프 반환


**type**   


**composedPath()**  


**stopPropagation()**    
: 이벤트 전파 중단


**stopImmediatePropagation()**  


**preventDefault()**    
: 이벤트 취소


**initEvent()**  



[top](#)
