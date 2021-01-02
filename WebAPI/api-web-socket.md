# WebSocket API
: 클라이언트와 서버 사이 양방향 통신을 위한 API     
: 연결을 위해 HTTP를 통해 WebSocket 핸드 셰이크를 수행    
: 연결이 되면 HTTP 프로토콜에서 웹소켓 프로토콜로 변경          
: HTTP/3 경우 UDP 기반이므로 새로운 웹소켓 프로토콜 필요 -- WebTransport   
: 웹소켓 프로토콜은 메시지 스트림만 지원   


https://html.spec.whatwg.org/multipage/web-sockets.html     
http://trac.webkit.org/browser/webkit/trunk/Source/WebCore/Modules/websockets    

**HTTP를 양방향 통신처럼 사용하는 기술**  
- Polling
- Long Polling
- Streaming


**api**
- [WebSocket](#websocket)
- [CloseEvent](#closeevent)


**Websocket Handshake**
```bash
# client request
GET /url HTTP/1.1
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Protocol:
Sec-WebSocket-Version:
Sec-WebSocket-Key:
...

# server response
HTTP/1.1 101 Switching Protocols
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Accept:
Sec-WebSocket-Protocol:
...
```



## WebSocket

```webidl
[Exposed=(Window,Worker)]
interface WebSocket : EventTarget {
  constructor(USVString url, optional (DOMString or sequence<DOMString>) protocols = []);

  readonly attribute USVString url;

  const unsigned short CONNECTING = 0;
  const unsigned short OPEN = 1;
  const unsigned short CLOSING = 2;
  const unsigned short CLOSED = 3;
  readonly attribute unsigned short readyState;
  readonly attribute unsigned long long bufferedAmount;

  attribute EventHandler onopen;
  attribute EventHandler onerror;
  attribute EventHandler onclose;
  readonly attribute DOMString extensions;
  readonly attribute DOMString protocol;
  undefined close(optional [Clamp] unsigned short code, optional USVString reason);

  attribute EventHandler onmessage;
  attribute BinaryType binaryType;
  undefined send(USVString data);
  undefined send(Blob data);
  undefined send(ArrayBuffer data);
  undefined send(ArrayBufferView data);
};

enum BinaryType { "blob", "arraybuffer" };
```


**readyState**   
: 현재 소켓의 연결 상태 반환

상태 | 값 | 설명
---|---|---
CONNECTING | 0 | 소켓이 생성중이며 연결되지 않은 상태  
OPEN       | 1 | 소켓이 연결되어 통신 가능 상태
CLOSING    | 2 | close() 메서드가 호출된 상태  
CLOSED     | 3 | 소켓 연결이 닫혔거나 열 수 없는 상태


ex.
```js
// 웹소켓 URL 체계
var socket = new WebSocket('ws://example.com/');
var socket = new WebSocket('wss://example.com/');

socket.onerror = function(e) {
    // 통신 오류
};

socket.onopen = function(e) {
    // 소켓 연결
};

socket.onclose = function(e) {
    // 소켓 연결 종료
};

socket.onmessage = function(e) {
    // 서버 응답 메시지
};
```



## CloseEvent

```webidl
[Exposed=(Window,Worker)]
interface CloseEvent : Event {
  constructor(DOMString type, optional CloseEventInit eventInitDict = {});

  readonly attribute boolean wasClean;
  readonly attribute unsigned short code;
  readonly attribute USVString reason;
};

dictionary CloseEventInit : EventInit {
  boolean wasClean = false;
  unsigned short code = 0;
  USVString reason = "";
};
```



[top](#)
