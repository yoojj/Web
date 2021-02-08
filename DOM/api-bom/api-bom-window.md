# WindowOrWorkerGlobalScope

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
  Promise<ImageBitmap> createImageBitmap(ImageBitmapSource image, long sx, long sy, long sw, long sh,
      optional ImageBitmapOptions options = {});
};

Window includes WindowOrWorkerGlobalScope;
WorkerGlobalScope includes WindowOrWorkerGlobalScope;
```


속성 | 설명
---|---
origin  | URL origin을 문자열로 반환  
isSecureContext     | 현재 컨텍스트가 안전한지 여부 반환
crossOriginIsolated |


**btoa()**   
: U+0000 ~ U+00FF 범위의 문자열을 Base64로 인코딩하고 반환  


**atob()**  
: Base64로 인코딩된 데이터를 디코딩하고 반환  


**setTimeout()**   
: 제한 시간 후 핸들러를 한 번만 호출  


**clearTimeout()**   
: 제한 시간 후 setTimeout() 제거   


**setInterval()**   
: 제한 시간마다 핸들러 호출


**clearInterval()**   
: 제한 시간 후 setInterval() 제거


**queueMicrotask()**    
:


**createImageBitmap()**   
:



# Window

https://html.spec.whatwg.org/multipage/window-object.html#window


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

  undefined postMessage(any message, USVString targetOrigin,
      optional sequence<object> transfer = []);
  undefined postMessage(any message,
      optional WindowPostMessageOptions options = {});
};

Window includes GlobalEventHandlers;
Window includes WindowEventHandlers;

dictionary WindowPostMessageOptions : PostMessageOptions {
  USVString targetOrigin = "/";
};
```


속성 | 설명
---|---
window   | 현재 Window 객체 반환
self     | 현재 Window 객체 반환
document | Document 객체 반환
name     | 윈도우 이름을 반환하거나 지정
location | Location 객체 반환
history  | History 객체 반환
customElements | CustomElementRegistry 객체 반환
locationbar  | locationbar가 표시되면 true 반환
menubar      | menubar가 표시되면 true 반환
personalbar  | personalbar가 표시되면 true 반환
scrollbars   | scrollbars가 표시되면 true 반환
statusbar    | statusbar가 표시되면 true 반환
toolbar      | toolbar가 표시되면 true 반환
status       | statusbar의 텍스트를 반환하거나 지정
closed       | 윈도우가 닫혀있으면 true 반환
frames       | WindowProxy 객체 반환
length       | 프레임 수 반환  
top          | 윈도우가 계층 구조를 형성한다면 최상위에 위치한 윈도우 반환
opener       |
parent       |
frameElement | Element 객체 반환
navigator    | Navigator 객체 반환
originAgentCluster |


**open()**   
: 전달 받은 URL을 표시하는 윈도우를 열고 about:blank 반환

```js
var target = '_blank';

var features = {
    // 윈도우 위치
    top: 0,
    left: 0,
    screenX: 0,
    screenY: 0,

    // 윈도우 크기
    width: 0,
    height: 0,
    innerWidth: 0,
    innerHeight: 0,

    // UI 표시
    menubar: true,
    toolbar: true,
    titlebar: true,
    status: true,
    location: true,
    resizable: true,
    scrollbars: true,
};

window.open('http://example.com', target, features);
```


## partial interface  

```webidl
partial interface Window {
  [NewObject] CSSStyleDeclaration getComputedStyle(Element elt, optional DOMString? pseudoElt);
};


partial interface Window {
    [NewObject] MediaQueryList matchMedia(DOMString query);
    [SameObject, Replaceable] readonly attribute Screen screen;

    void moveTo(long x, long y);
    void moveBy(long x, long y);
    void resizeTo(long x, long y);
    void resizeBy(long x, long y);

    [Replaceable] readonly attribute long innerWidth;
    [Replaceable] readonly attribute long innerHeight;

    [Replaceable] readonly attribute double scrollX;
    [Replaceable] readonly attribute double pageXOffset;
    [Replaceable] readonly attribute double scrollY;
    [Replaceable] readonly attribute double pageYOffset;
    void scroll(optional ScrollToOptions options);
    void scroll(unrestricted double x, unrestricted double y);
    void scrollTo(optional ScrollToOptions options);
    void scrollTo(unrestricted double x, unrestricted double y);
    void scrollBy(optional ScrollToOptions options);
    void scrollBy(unrestricted double x, unrestricted double y);

    [Replaceable] readonly attribute long screenX;
    [Replaceable] readonly attribute long screenY;
    [Replaceable] readonly attribute long outerWidth;
    [Replaceable] readonly attribute long outerHeight;
    [Replaceable] readonly attribute double devicePixelRatio;
};

dictionary ScrollToOptions : ScrollOptions {
    unrestricted double left;
    unrestricted double top;
};

dictionary ScrollOptions {
    ScrollBehavior behavior = "auto";
};

enum ScrollBehavior { "auto", "instant", "smooth" };
```


속성 | 설명
---|---
screen      | 현재 윈도우와 관련된 Screen 객체 반환   
innerWidth  | 스크롤을 포함한 윈도우의 뷰포트 너비 반환  
innerHeight | 스크롤을 포함한 윈도우의 뷰포트 높이 반환  
scrollX     |
scrollY     |
pageXOffset | 
pageYOffset |
screenX     |
screenY     |
outerWidth  | 윈도우의 너비 반환
outerHeight | 윈도우의 높이 반환
devicePixelRatio | 현재 표시 장치의 물리적 픽셀과 CSS 픽셀의 비율 반환


**getComputedStyle()**  
: 전달받은 요소의 모든 CSS 속성을 담은 CSSStyleDeclaration 객체 반환

```js
var css = window.getComputedStyle('el');
```


**matchMedia()**   
: 전달받은 미디어 쿼리에 대한 MediaQueryList 객체 반환  

```js
var mq = window.matchMedia('min-width:300px');
```



[top](#)
