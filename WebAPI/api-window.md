# Window API    

- WindowOrWorkerGlobalScope
- Window



## WindowOrWorkerGlobalScope
: Window와 WorkerGlobalScope에 기능 제공   

https://html.spec.whatwg.org/multipage/webappapis.html#windoworworkerglobalscope


```webidl
interface mixin WindowOrWorkerGlobalScope {
  [Replaceable] readonly attribute USVString origin;
  readonly attribute boolean isSecureContext;
  readonly attribute boolean crossOriginIsolated;

  DOMString btoa(DOMString data);
  ByteString atob(DOMString data);

  long setTimeout(TimerHandler handler, optional long timeout = 0, any... arguments);
  undefined clearTimeout(optional long handle = 0);
  long setInterval(TimerHandler handler, optional long timeout = 0, any... arguments);
  undefined clearInterval(optional long handle = 0);

  undefined queueMicrotask(VoidFunction callback);

  Promise<ImageBitmap> createImageBitmap(ImageBitmapSource image, optional ImageBitmapOptions options = {});
  Promise<ImageBitmap> createImageBitmap(ImageBitmapSource image, long sx, long sy, long sw, long sh, optional ImageBitmapOptions options = {});
};

Window includes WindowOrWorkerGlobalScope;
WorkerGlobalScope includes WindowOrWorkerGlobalScope;

typedef (DOMString or Function) TimerHandler;
```


**btoa()**   
: U+0000 ~ U+00FF 범위의 문자열을 Base64로 인코딩하고 반환  


**atob()**  
: Base64로 인코딩된 데이터를 디코딩하고 반환  


**setTimeout()**   
: 제한 시간 후 핸들러를 한 번만 실행


**clearTimeout()**   
: setTimeout() 취소   


**setInterval()**   
: 제한 시간마다 핸들러 실행


**clearInterval()**   
: setInterval() 취소



## Window
: WindowOrWorkerGlobalScope 구현

https://html.spec.whatwg.org/multipage/window-object.html


```webidl
[Global=Window, Exposed=Window,LegacyUnenumerableNamedProperties]
interface Window : EventTarget {
  [LegacyUnforgeable] readonly attribute WindowProxy window;
  [Replaceable] readonly attribute WindowProxy self;
  [LegacyUnforgeable] readonly attribute Document document;
  attribute DOMString name;
  [PutForwards=href, LegacyUnforgeable] readonly attribute Location location;
  readonly attribute History history;
  readonly attribute CustomElementRegistry customElements;
  [Replaceable] readonly attribute BarProp locationbar;
  [Replaceable] readonly attribute BarProp menubar;
  [Replaceable] readonly attribute BarProp personalbar;
  [Replaceable] readonly attribute BarProp scrollbars;
  [Replaceable] readonly attribute BarProp statusbar;
  [Replaceable] readonly attribute BarProp toolbar;
  attribute DOMString status;
  undefined close();
  readonly attribute boolean closed;
  undefined stop();
  undefined focus();
  undefined blur();

  [Replaceable] readonly attribute WindowProxy frames;
  [Replaceable] readonly attribute unsigned long length;
  [LegacyUnforgeable] readonly attribute WindowProxy? top;
  attribute any opener;
  [Replaceable] readonly attribute WindowProxy? parent;
  readonly attribute Element? frameElement;
  WindowProxy? open(optional USVString url = "",
    optional DOMString target = "_blank",
    optional [LegacyNullToEmptyString] DOMString features = "");
  getter object (DOMString name);

  readonly attribute Navigator navigator;
  readonly attribute boolean originAgentCluster;

  undefined alert();
  undefined alert(DOMString message);
  boolean confirm(optional DOMString message = "");
  DOMString? prompt(optional DOMString message = "", optional DOMString default = "");
  undefined print();

  undefined postMessage(
      any message, USVString targetOrigin,
      optional sequence<object> transfer = []);
  undefined postMessage(any message,
      optional WindowPostMessageOptions options = {});
};

Window includes GlobalEventHandlers;
Window includes WindowEventHandlers;

dictionary WindowPostMessageOptions : PostMessageOptions {
  USVString targetOrigin = "/";
};


[Exposed=Window]
interface BarProp {
  readonly attribute boolean visible;
};
```


**속성**

속성 | 설명
---|---
window   | 현재 윈도우 객체 반환
self     | 현재 윈도우 객체 반환
frames   | 현재 윈도우(WindowProxy) 객체 반환
top      |
parent   |
name     | 윈도우 이름을 반환하거나 이름 지정
status   | statusbar의 텍스트를 반환하거나 지정
closed   | 윈도우가 닫혀있으면 true 반환
length   |
opener   |
document | Document 객체 반환
location | Location 객체 반환
history  | History 객체 반환
navigator| Navigator 객체 반환
customElements | CustomElementRegistry 객체 반환
frameElement   | Element 객체 반환
locationbar | locationbar가 표시되면 true 반환
menubar     | menubar가 표시되면 true 반환
personalbar | personalbar가 표시되면 true 반환
scrollbars  | scrollbars가 표시되면 true 반환
statusbar   | statusbar가 표시되면 true 반환
toolbar     | toolbar가 표시되면 true 반환



**메소드**

메소드 | 설명
---|---
object() |
close()  | 윈도우를 닫음
stop()   | Document 로드를 취소함
focus()  | 요소로 포커스 이동
blur()   | 포커스를 뷰포트로 이동
open()   | 새 윈도우
alert()  | 모달 표시
confirm()| 사용자의 응답을 받는 모달 표시   
prompt() | 사용자의 텍스트를 받는 모달 표시
print()  | 페이지 인쇄 메시지 표시  



[top](#)
