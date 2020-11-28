# HTML Attribute   
: 요소에 추가적인 기능이나 동작 제어를 위해 사용    
: 꼭 포함해야 하는 필수 속성이 존재     

**property**     
: DOM 객체에서 attribute를 지칭하는 표현    

- attribute : HTML, 정적     
- property : DOM, 동적  


**속성 종류**   
- [전역 속성](#global-attributes)
- [이벤트 속성](#event-attributes)
- [불리언 속성](#boolean-attributes)
- 필수 속성
- 선택적 속성


```html
<tag attributes-name="attributes value">


<!-- 필수 속성 -->
<img src="">

<!-- 후크 속성 -->
<p class=""></p>

<!-- 빈 속성 -->
<input autofocus>
```



## Global Attributes
= Standard Attributes   
: 비표준 태그를 포함한 모든 태그에서 사용 가능한 속성

https://html.spec.whatwg.org/multipage/dom.html#global-attributes

전역 속성 | 설명
---|---
accesskey        | 현재 요소에 접근하는 키보드 단축키 지정
autocapitalize   | 텍스트 입력이나 편집시 대소문자 변환 여부 지정  
autofocus        | 웹 문서 로드시 포커스되어야 하는 요소에 지정 -- 불리언 속성     
contenteditable  | 요소의 콘텐츠 편집 여부 지정
dir              | 요소의 텍스트 방향 지정
draggable        | 요소의 드래그 여부 지정
enterkeyhint     | 가상 키보드의 엔터키에 액션에 대한 힌트나 아이콘 지정
hidden           | 요소를 숨기며 렌더링 하지 않음 -- 불리언 속성
inputmode        | 가상 키보드 선택을 위한 힌트 지정     
is               | 요소가 사용자 정의 요소처럼 동작하도록 지정
itemid           | 아이템 식별자
itemprop         | 아이템 항목에 속성 추가
itemref          | 마이크로데이터 - 특성 지정  
itemscope        | 마이크로데이터 - 범위-컨테이너 요소 지정 -- 불리언 속성
itemtype         | 마이크로데이터 - 어휘 지정
lang             | 요소의 언어 명시
nonce            | 콘텐츠 보안 정책(CPU)을 위해 한 번만 사용하는 임시 값 지정  
spellcheck       | 철자-문법 검사 여부 지정
style            | 해당 요소의 인라인 스타일 지정
tabindex         | 탭키를 사용해 포커스 이동시 순서 지정
title            | 요소에 대해 추가 정보 지정
translate        | 요소의 일부 속성과 텍스트 콘텐츠의 번역 여부 지정


```html
<tag accesskey="a b c"></tag>
<!--
: 여러 단축키 지정시 공백으로 분리   
: 지정한 순서로 우선 순위를 갖음  
-->


<tag autocapitalize="characters"></tag>
<!-- 모든 문자 대문자 -->

<tag autocapitalize="words"></tag>
<!-- 단어의 첫 글자 대문자 -->

<tag autocapitalize="on | sentences"></tag>
<!-- 문장의 첫 글자 대문자 -->

<tag autocapitalize="off | none"></tag>
<!-- 모든 문자 소문자 -->


<tag autofocus></tag>


<tag contenteditable="true | false"></tag>


<tag dir="ltr | rtl | auto"></tag>
<!-- auto일 경우 브라우저가 선택 -->


<tag draggable="true | false | auto"></tag>


<tag enterkeyhint="enter | done | go | next | previous | search | send"></tag>


<tag hidden></tag>


<tag inputmode="none | text | url | email | search | tel | numeric | decimal "></tag>
<!--
- none : 가상 키보드를 표시하지 않음
- numeric : 숫자 입력이 가능한 가상 키보드 표시
- decimal : 분수 입력이 가능한 가상 키보드 표시
- decimal : 검색에 최적화 된 가상 키보드 표시
-->


<tag is="test-is"><tag>
<script>
class TestIs extends HTMLParagraphElement { .. }

customElements.define('test-is', TestIs, { extends: 'tag' });
</script>


<tag nonce="토큰"></tag>


<tag translate="yes | no"></tag>
<!--
번역 가능한 속성
- title 속성
- area, img, input 태그의 alt 속성
- a, area의 download 속성
- ...
-->
```



## Event Attributes

### 윈도우 이벤트

이벤트 속성 | 설명
---|---
onafterprint   | 웹 문서를 프린트한 직후에 실행되는 이벤트
onbeforeprint  | 웹 문서를 프린트하기 전에 실행되는 이벤트
onbeforeunload |
onhashchange   |
onload         |
onlanguagechange  |
onmessage      |
onmessageerror |
onoffline      |
ononline       |
onpagehide     |
onpageshow     |
onpopstate     |
onrejectionhandled |
onresize  |
onstorage | 웹 스토리지 업데이트시 실행되는 이벤트
onunhandledrejection |  
onunload  | 브라우저 창이 닫히기 전 실행되는 이벤트



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
onselect  |
onslotchange |
onsearch  | 검색 필드에서 텍스트 입력시 발생하는 이벤트
onsubmit  | 양식 제출시 발생하는 이벤트



### 키보드 이벤트

이벤트 속성 | 설명
---|---
onkeydown  | 키보드를 누를 때 발생하는 이벤트
onkeypress | 키보드를 눌러 실제로 텍스트가 삽입될 때 발생하는 이벤트
onkeyup    | 키보드를 놓을 때 발생하는 이벤트  



### 마우스 이벤트

이벤트 속성 | 설명
---|---
onauxclick  |
onclick     | 마우스 클릭시 발생하는 이벤트
ondblclick  | 마우스 더블 클릭시 발생하는 이벤트
oncontextmenu | 컨텍스트 메뉴를 트리거 할 때 발생하는 이벤트   
ondrag      | 요소 드래그시 발생하는 이벤트
ondragend   |
ondragenter |
ondragleave |
ondragover  |
ondragstart |
ondrop	    |
onmousedown |
onmouseenter|
onmouseleave|
onmousemove |
onmouseout  |
onmouseover |
onmouseup   |
onscroll    |
onshow      |
ontoggle    |
onwheel     | 요소에서 마우스 휠 사용시 발생하는 이벤트



### 클립 보드 이벤트

이벤트 속성 | 설명
---|---
oncopy  | 요소나 요소의 콘텐츠를 복사할 때 발생되는 이벤트  
oncut   | 요소나 요소의 콘텐츠를 잘라내거나 삭제할 때 발생되는 이벤트   
onpaste | 콘텐츠를 붙여 넣을때 발생되는 이벤트



### 미디어 이벤트 속성

이벤트 속성 | 설명
---|---
onabort      |
oncanplay    |
oncanplaythrough |
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
onreadystatechange |
onseeked     |
onseeking    |
onstalled    |
onsuspend    |
ontimeupdate |
onvolumechange  |
onwaiting    |



## Boolean Attributes  
: 약 25개의 불리언 속성 존재    
: true이면 속성을 표기하고 false면 속성을 생략함   

```
allowfullscreen
allowpaymentrequest
async
autofocus
autoplay
checked
controls
default
disabled
formnovalidate
hidden
ismap
itemscope
loop
multiple
muted
nomodule
novalidate
open
playsinline
readonly
required
reversed
selected
truespeed
```


[top](#)
