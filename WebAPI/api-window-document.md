# Document API

https://html.spec.whatwg.org/multipage/dom.html#the-document-object



## Document
: GlobalEventHandlers와 DocumentAndElementEventHandlers 구현

GlobalEventHandlers  
 DocumentAndElementEventHandlers  
https://github.com/yoojj/Web/blob/master/WebAPI/api-event.md


```webidl
[LegacyOverrideBuiltIns]
partial interface Document {
  [PutForwards=href, LegacyUnforgeable] readonly attribute Location? location;
  attribute USVString domain;
  readonly attribute USVString referrer;
  attribute USVString cookie;
  readonly attribute DOMString lastModified;
  readonly attribute DocumentReadyState readyState;

  getter object (DOMString name);
  [CEReactions] attribute DOMString title;
  [CEReactions] attribute DOMString dir;
  [CEReactions] attribute HTMLElement? body;
  readonly attribute HTMLHeadElement? head;
  [SameObject] readonly attribute HTMLCollection images;
  [SameObject] readonly attribute HTMLCollection embeds;
  [SameObject] readonly attribute HTMLCollection plugins;
  [SameObject] readonly attribute HTMLCollection links;
  [SameObject] readonly attribute HTMLCollection forms;
  [SameObject] readonly attribute HTMLCollection scripts;
  NodeList getElementsByName(DOMString elementName);
  readonly attribute HTMLOrSVGScriptElement? currentScript;

  [CEReactions] Document open(optional DOMString unused1, optional DOMString unused2);
  WindowProxy? open(USVString url, DOMString name, DOMString features);
  [CEReactions] undefined close();
  [CEReactions] undefined write(DOMString... text);
  [CEReactions] undefined writeln(DOMString... text);

  readonly attribute WindowProxy? defaultView;
  boolean hasFocus();
  [CEReactions] attribute DOMString designMode;
  [CEReactions] boolean execCommand(DOMString commandId, optional boolean showUI = false, optional DOMString value = "");
  boolean queryCommandEnabled(DOMString commandId);
  boolean queryCommandIndeterm(DOMString commandId);
  boolean queryCommandState(DOMString commandId);
  boolean queryCommandSupported(DOMString commandId);
  DOMString queryCommandValue(DOMString commandId);

  [LegacyLenientThis] attribute EventHandler onreadystatechange;

};

Document includes GlobalEventHandlers;
Document includes DocumentAndElementEventHandlers;

enum DocumentReadyState { "loading", "interactive", "complete" };

typedef (HTMLScriptElement or SVGScriptElement) HTMLOrSVGScriptElement;
```


속성 | 설명
---|---
location |
domain   | 페이지의 도메인을 반환하거나 지정  
referrer | 방문한 페이지의 url을 반환
cookie   | HTTP 쿠키 반환
lastModified  | 페이지가 마지막으로 수정된 날짜와 시간 반환
readyState    | 페이지 로드 상태 반환  
title    | 페이지의 title 요소의 텍스트 콘텐츠 반환  
dir      | 페이지의 텍스트 방향 반환  
body     | 페이지의 body 요소 반환
head     | 페이지의 head 요소 반환
images   | 페이지의 img 요소들을 반환하고 없으면 빈 배열 반환
embeds   | 페이지의 object 요소들을 반환하고 없으면 빈 배열 반환
plugins  | 페이지의 embed 요소들을 반환하고 없으면 빈 배열 반환
links    | 페이지의 href 속성을 갖는 a 요소들을 반환하고 없으면 빈 배열 반환
forms    | 페이지의 form 요소들을 반환하고 없으면 빈 배열 반환
scripts  | 페이지의 script 요소들을 반환하고 없으면 빈 배열 반환
currentScript | 현재 실행중인 스크립트의 요소 반환  


**readyState**  
: 페이지 로드 단계에 따라 3가지 상태 반환    
: 상태가 변경될 때마다 readystatechange 이벤트 발생      

- loading : 페이지 로드중
- interactive : 페이지는 로드되었으나 css나 이미지같은 리소스가 로드 중
- complete : 페이지 로드 완료


**getElementsByName()**   
: 요소의 name 속성과 일치하는 요소 반환  

```html
<input type="checkbox" name="input">

<script>
document.getElementsByName('input')[0].checked = true;
</script>
```



[top](#)
