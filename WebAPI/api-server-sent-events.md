# SSE API   
Server-Sent Events   
: 서버의 데이터를 자동으로 수신하기 위한 API      


https://html.spec.whatwg.org/multipage/server-sent-events.html


**SSE vs WebSocket**   
: SSE와 WebSocket 모두 서버 푸시 기능 지원      
: SSE은 단방향 통신을 WebSocket은 양방향 통신을 지원     
: SSE은 HTTP 프로토콜을 WebSocket은 웹소켓 프로토콜을 사용  



## EventSource

```webidl
[Exposed=(Window,Worker)]
interface EventSource : EventTarget {
  constructor(USVString url, optional EventSourceInit eventSourceInitDict = {});

  readonly attribute USVString url;
  readonly attribute boolean withCredentials;

  const unsigned short CONNECTING = 0;
  const unsigned short OPEN = 1;
  const unsigned short CLOSED = 2;
  readonly attribute unsigned short readyState;

  attribute EventHandler onopen;
  attribute EventHandler onmessage;
  attribute EventHandler onerror;
  undefined close();
};

dictionary EventSourceInit {
  boolean withCredentials = false;
};
```


**readyState**   
: EventSource 객체의 연결 상태 반환

상태 | 값 | 설명
---|---|---
CONNECTING | 0 | 연결되지 않은 상태  
OPEN       | 1 | 연결되어 메시지 수신이 가능한 상태
CLOSED     | 2 | close()가 호출되었거나 오류로 인해 연결이 닫힌 상태  


ex.
```js
// example.html의 HTTP 헤더 content-type 속성은 text/event-stream
var event = new EventSource('example.html');

event.onerror = (e) => {
    // 연결 오류
}

event.onopen = (e) => {
    // 서버와 연결
}

event.onmessage = (e) => {
    // 서버 메시지 수신  
}
```



[top](#)
