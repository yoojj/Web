# Event API

https://html.spec.whatwg.org/multipage/webappapis.html


**api**
- [ErrorEvent](#errorevent)
- [GlobalEventHandlers](#globaleventhandlers)
- [WindowEventHandlers](#windoweventhandlers)
- [DocumentAndElementEventHandlers](#documentandelementeventhandlers)



## ErrorEvent

```webidl
[Exposed=(Window,Worker)]
interface ErrorEvent : Event {
  constructor(DOMString type, optional ErrorEventInit eventInitDict = {});

  readonly attribute DOMString message;
  readonly attribute USVString filename;
  readonly attribute unsigned long lineno;
  readonly attribute unsigned long colno;
  readonly attribute any error;
};

dictionary ErrorEventInit : EventInit {
  DOMString message = "";
  USVString filename = "";
  unsigned long lineno = 0;
  unsigned long colno = 0;
  any error = null;
};
```



## GlobalEventHandlers

```webidl
interface mixin GlobalEventHandlers {
  attribute EventHandler onabort;
  attribute EventHandler onauxclick;
  attribute EventHandler onblur;
  attribute EventHandler oncancel;
  attribute EventHandler oncanplay;
  attribute EventHandler oncanplaythrough;
  attribute EventHandler onchange;
  attribute EventHandler onclick;
  attribute EventHandler onclose;
  attribute EventHandler oncontextmenu;
  attribute EventHandler oncuechange;
  attribute EventHandler ondblclick;
  attribute EventHandler ondrag;
  attribute EventHandler ondragend;
  attribute EventHandler ondragenter;
  attribute EventHandler ondragleave;
  attribute EventHandler ondragover;
  attribute EventHandler ondragstart;
  attribute EventHandler ondrop;
  attribute EventHandler ondurationchange;
  attribute EventHandler onemptied;
  attribute EventHandler onended;
  attribute OnErrorEventHandler onerror;
  attribute EventHandler onfocus;
  attribute EventHandler onformdata;
  attribute EventHandler oninput;
  attribute EventHandler oninvalid;
  attribute EventHandler onkeydown;
  attribute EventHandler onkeypress;
  attribute EventHandler onkeyup;
  attribute EventHandler onload;
  attribute EventHandler onloadeddata;
  attribute EventHandler onloadedmetadata;
  attribute EventHandler onloadstart;
  attribute EventHandler onmousedown;
  [LegacyLenientThis] attribute EventHandler onmouseenter;
  [LegacyLenientThis] attribute EventHandler onmouseleave;
  attribute EventHandler onmousemove;
  attribute EventHandler onmouseout;
  attribute EventHandler onmouseover;
  attribute EventHandler onmouseup;
  attribute EventHandler onpause;
  attribute EventHandler onplay;
  attribute EventHandler onplaying;
  attribute EventHandler onprogress;
  attribute EventHandler onratechange;
  attribute EventHandler onreset;
  attribute EventHandler onresize;
  attribute EventHandler onscroll;
  attribute EventHandler onsecuritypolicyviolation;
  attribute EventHandler onseeked;
  attribute EventHandler onseeking;
  attribute EventHandler onselect;
  attribute EventHandler onslotchange;
  attribute EventHandler onstalled;
  attribute EventHandler onsubmit;
  attribute EventHandler onsuspend;
  attribute EventHandler ontimeupdate;
  attribute EventHandler ontoggle;
  attribute EventHandler onvolumechange;
  attribute EventHandler onwaiting;
  attribute EventHandler onwebkitanimationend;
  attribute EventHandler onwebkitanimationiteration;
  attribute EventHandler onwebkitanimationstart;
  attribute EventHandler onwebkittransitionend;
  attribute EventHandler onwheel;
};
```

이벤트 속성 | 설명
---|---
onload    | 웹 문서가 로드되면 발생하는 이벤트
onresize  | 브라우저 크기가 바뀌면 발생하는 이벤트  
onwebkitanimationend | CSS 애니메이션이 완료된 경우 발생하는 이벤트
onwebkitanimationiteration | 반복되는 CSS 애니메이션이 종료되고 반복이 시작될 경우 발생하는 이벤트
onwebkitanimationstart |
onwebkittransitionend  |



### 양식 이벤트

이벤트 속성 | 설명
---|---
oncancel  |
onclose   |
onblur    | 요소의 포커스를 잃으면 발생하는 이벤트
onchange  | 요소의 상태를 변경하면 발생하는 이벤트
onfocus   | 요소에 포커스되면 발생하는 이벤트
onformdata|
oninput   | 요소의 값을 변경하면 발생하는 이벤트
oninvalid | 유효성 검사 중 제약 조건을 충족하지 못하면 발생하는 이벤트
onreset   | 양식 리셋시 발생하는 이벤트
onsecuritypolicyviolation | 콘텐츠 보안 정책 위반시 발생하는 이벤트
onselect  | 요소나 요소의 텍스트 콘텐츠가 선택될 경우 발생하는 이벤트
onslotchange |
onsearch  | 검색 필드에서 텍스트 입력시 발생하는 이벤트
onsubmit  | 양식 제출시 발생하는 이벤트



### 마우스 이벤트

이벤트 속성 | 설명
---|---
onauxclick  |
onclick     | 마우스 클릭시 발생하는 이벤트
ondblclick  | 마우스 더블 클릭시 발생하는 이벤트
oncontextmenu | 컨텍스트 메뉴를 트리거 할 때 발생하는 이벤트
ondrag      | 요소 드래그시 발생하는 이벤트
ondragend   | 드래그가 끝났을 경우 발생하는 이벤트
ondragenter | 드래그한 요소가 드롭 대상 위에 올라간 경우 발생하는 이벤트  
ondragleave | 드래그한 요소가 드롭 대상을 벗어날 경우 발생하는 이벤트
ondragover  | 드래그한 요소가 드롭 대상 위를 지나갈 경우 발생하는 이벤트
ondragstart | 드래그 시작시 발생하는 이벤트
ondrop	    | 드래그한 요소를 드롭할 경우 발생하는 이벤트  
onmousedown | 마우스 버튼 클릭시 발생하는 이벤트
onmouseenter|
onmouseleave|
onmousemove | 해당 영역에 마우스 포인터가 움직일 경우 발생하는 이벤트
onmouseout  | 마우스 포인터가 해당 영역을 벗어날 경우 발생하는 이벤트
onmouseover | 마우스 포인터가 해당 영역을 들어올 경우 발생하는 이벤트
onmouseup   | 클릭한 마우스 버튼을 뗄 경우 발생하는 이벤트
onscroll    | 스크롤 할 경우 발생하는 이벤트
ontoggle    | details 요소를 토글할 경우 발생하는 이벤트
onwheel     | 요소에서 마우스 휠 사용시 발생하는 이벤트


**onclick vs onmousedown**  
: onclick은 왼쪽 버튼만 적용되며 onmousedown는 양쪽 버튼과 휠 클릭 모두 적용



### 키보드 이벤트

이벤트 속성 | 설명
---|---
onkeydown  | 키보드를 누를 때 발생하는 이벤트
onkeypress | 키보드를 눌러 실제로 텍스트가 삽입될 때 발생하는 이벤트
onkeyup    | 키보드를 놓을 때 발생하는 이벤트  



### 미디어 이벤트

이벤트 속성 | 설명
---|---
onabort      | 미디어 데이터 로드가 중단되는 경우 발생하는 이벤트
oncanplay    | 미디어 재생이 가능하면 발생하는 이벤트
oncanplaythrough | 미디어 재생 준비가 (버퍼링 될 필요없이) 완료되면 발생하는 이벤트
oncuechange  |
ondurationchange |
onemptied    |
onended      |
onerror      |
onloadeddata |
onloadedmetadata |
onloadstart  |
onpause      |
onplay       |
onplaying    |
onprogress   |
onratechange |
onseeked     |
onseeking    |
onstalled    |
onsuspend    | 브라우저에 의해 미디어 데이터 로드를 중단 할 경우 발생하는 이벤트
ontimeupdate | 미디어 재생 위치가 변경되면 발생하는 이벤트
onvolumechange  | 미디어 볼륨이 변경되면 발생하는 이벤트
onwaiting    | 미디어 재생 중 버퍼링으로 재생이 정지되면 발생하는 이벤트



## WindowEventHandlers

```webidl
interface mixin WindowEventHandlers {
  attribute EventHandler onafterprint;
  attribute EventHandler onbeforeprint;
  attribute OnBeforeUnloadEventHandler onbeforeunload;
  attribute EventHandler onhashchange;
  attribute EventHandler onlanguagechange;
  attribute EventHandler onmessage;
  attribute EventHandler onmessageerror;
  attribute EventHandler onoffline;
  attribute EventHandler ononline;
  attribute EventHandler onpagehide;
  attribute EventHandler onpageshow;
  attribute EventHandler onpopstate;
  attribute EventHandler onrejectionhandled;
  attribute EventHandler onstorage;
  attribute EventHandler onunhandledrejection;
  attribute EventHandler onunload;
};
```


이벤트 속성 | 설명
---|---
onafterprint   | 웹 문서를 프린트한 직후에 실행되는 이벤트
onbeforeprint  | 웹 문서를 프린트하기 전에 실행되는 이벤트
onbeforeunload | 웹 문서를 언로드하려고 할 때 실행되는 이벤트
onhashchange   | 해시가 변경될 경우 실행되는 이벤트
onlanguagechange | 언어가 변경될 경우 실행되는 이벤트
onmessage      | 메시지를 받을 경우 실행되는 이벤트
onmessageerror | 역직렬화를 할 수 없는 메시지를 받은 경우 실행되는 이벤트
onoffline      | 네트워크 연결을 실패할 경우 실행되는 이벤트
ononline       | 네트워크 연결이 반환될 경우 실행되는 이벤트
onpagehide     |
onpageshow     |
onpopstate     | 세션 기록을 탐색할 때 호출되는 이벤트
onrejectionhandled |
onstorage      | 웹 스토리지 업데이트시 실행되는 이벤트
onunhandledrejection |  
onunload       | 브라우저 창이 닫히기 전 실행되는 이벤트



## DocumentAndElementEventHandlers

```webidl
interface mixin DocumentAndElementEventHandlers {
  attribute EventHandler oncopy;
  attribute EventHandler oncut;
  attribute EventHandler onpaste;
};
```

이벤트 속성 | 설명
---|---
oncopy  | 요소나 요소의 콘텐츠를 복사할 때 발생하는 이벤트  
oncut   | 요소나 요소의 콘텐츠를 잘라내거나 삭제할 때 발생하는 이벤트   
onpaste | 콘텐츠를 붙여 넣을때 발생하는 이벤트



[top](#)
