# HTML Attribute   
: 요소에 추가적인 기능이나 동작 제어를 위해 사용    
: 꼭 포함해야 하는 필수 속성이 존재     


**property**     
: DOM 객체에서 attribute를 지칭하는 표현    

attribute : HTML, 정적       
property : DOM, 동적    


**속성 분류**   
- [전역 속성](#global-attributes)
- [이벤트 속성](#event-attributes)
- [불리언 속성](#boolean-attributes)
- 필수 속성
- 선택적 속성

ex.
```html
<!-- 필수 속성 -->
<img src="">

<!-- 후크 속성 -->
<p class=""></p>

<!-- 불리언 속성 -->
<input type="text" autofocus>
```



## Global Attributes
= Standard Attributes   
: 비표준 태그를 포함한 모든 태그에서 사용 가능한 속성

https://html.spec.whatwg.org/multipage/dom.html#global-attributes

전역 속성 | 설명
---|---   
accesskey        | 요소에 접근 가능한 키보드 단축키 지정
autocapitalize   | 텍스트 입력이나 편집시 대소문자 변환 여부 지정  
autofocus        | 웹 문서 로드시 포커스되어야 하는 요소에 지정 (불리언 속성)     
contenteditable  | 요소의 콘텐츠 편집 여부 지정
dir              | 요소의 텍스트 방향 지정
draggable        | 요소의 드래그 여부 지정
enterkeyhint     | 가상 키보드의 엔터키에 액션에 대한 힌트나 아이콘 지정
hidden           | 요소를 숨기며 렌더링 하지 않음 (불리언 속성)
inputmode        | 가상 키보드 선택을 위한 힌트 지정     
is               | 요소가 사용자 정의 요소처럼 동작하도록 지정
itemid           | 아이템 식별자
itemprop         | 아이템 항목에 속성 추가
itemref          | 마이크로데이터 : 특성 지정  
itemscope        | 마이크로데이터 : 범위-컨테이너 요소 지정 (불리언 속성)
itemtype         | 마이크로데이터 : 어휘 지정
lang             | 요소의 언어 명시
nonce            | 콘텐츠 보안 정책을 위해 한 번만 사용하는 임시 값 지정  
spellcheck       | 철자-문법 검사 여부 지정
style            | 요소의 인라인 스타일 지정
tabindex         | 탭키 사용시 요소들이 포커스되는 순서 지정
title            | 요소에 대해 추가 정보 지정
translate        | 요소의 (일부) 속성과 텍스트 콘텐츠 번역 여부 지정


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
<!-- 하나의 웹 문서에 한 번만 적용 -->


<tag contenteditable="true | false"></tag>


<tag dir="ltr | rtl | auto"></tag>
<!--
: 전역 사용을 위해서는 html 태그에서 명시  

- ltr : left to right
- rtl : right to left
- auto : 브라우저 설정에 따름
-->


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


<tag lang="ko">
<tag lang="ko-KR">
<!--
: 검색 엔진, 텍스트 리더기, 번역기 등을 위해 문서에 쓰인 대표적인 언어 명시
: 전역 사용을 위해서는 html 태그에서 명시  

ko : 언어 코드 지정
ko-KR : 언어 코드 + 국가 코드 지정

언어 코드 리스트
https://www.sitepoint.com/iso-2-letter-language-codes/
-->


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
: 이벤트 속성은 모든 태그에서 사용 가능   


### 글로벌 이벤트

**GlobalEventHandlers**    
https://github.com/yoojj/Web/blob/master/DOM/api-html/api-html-events.md#globaleventhandlers

- onabort
- onauxclick
- onblur
- oncancel
- oncanplay
- oncanplaythrough
- onchange
- onclick
- onclose
- oncontextmenu
- oncuechange
- ondblclick
- ondrag
- ondragend
- ondragenter
- ondragleave
- ondragover
- ondragstart
- ondrop
- ondurationchange
- onemptied
- onended
- onerror
- onfocus
- onformdata
- oninput
- oninvalid
- onkeydown
- onkeypress
- onkeyup
- onload
- onloadeddata
- onloadedmetadata
- onloadstart
- onmousedown
- onmouseenter
- onmouseleave
- onmousemove
- onmouseout
- onmouseover
- onmouseup
- onpause
- onplay
- onplaying
- onprogress
- onratechange
- onreset
- onresize
- onscroll
- onsecuritypolicyviolation
- onseeked
- onseeking
- onselect
- onslotchange
- onstalled
- onsubmit
- onsuspend
- ontimeupdate
- ontoggle
- onvolumechange
- onwaiting
- onwebkitanimationend
- onwebkitanimationiteration
- onwebkitanimationstart
- onwebkittransitionend
- onwheel



### 윈도우 이벤트

**WindowEventHandlers**   
https://github.com/yoojj/Web/blob/master/DOM/api-html/api-html-events.md#windoweventhandlers

- onafterprint
- onbeforeprint
- onbeforeunload
- onhashchange
- onlanguagechange
- onmessage
- onmessageerror
- onoffline
- ononline
- onpagehide
- onpageshow
- onpopstate
- onrejectionhandled
- onstorage
- onunhandledrejection
- onunload


```js
// 웹 문서끼리 메시지를 주고 받음
window.parent.postMessage('메시지', '*');


window.onmessage = e => {
    console.log(e.data);
}
window.addEventListener('message', e => {
    console.log(e.data);
});


window.onpagehide = e => {}
window.addEventListener('pagehide', e => {});


window.onunhandledrejection = e => {
    console.log(e.detail);
    console.log(e.reason);
}
```


### 클립 보드 이벤트

**DocumentAndElementEventHandlers**    
https://github.com/yoojj/Web/blob/master/DOM/api-html/api-html-events.md#documentandelementeventhandlers

- oncopy   
- oncut
- onpaste



## Boolean Attributes  
: 약 25개의 불리언 속성 존재    
: true이면 속성을 표기하고 false면 속성을 생략함   

속성 | 설명
---|---
allowfullscreen     |
allowpaymentrequest |
async          | script 태그의 리소스를 비동기적으로 로드하는지 여부 지정  
autofocus      | 웹 문서 로드시 포커스되어야 하는 요소에 지정
autoplay       | audio, video 태그의 콘텐츠 자동 재생 지정
checked        |
controls       | audio, video 태그의 콘텐츠 제어를 위한 컨트롤 표시  
default        |
disabled       | 요소 비활성화 지정
formnovalidate |
hidden      |
ismap       |
itemscope   |
loop        | audio, video 태그의 콘텐츠 반복 재생 지정  
multiple    | 일부 입력 필드에 하나 이상의 값을 입력 가능하게 함
muted       | audio, video 태그의 콘텐츠 음소거 지정  
nomodule    |
novalidate  | 유효성 검사를 수행하지 않도록 지정
open        | details 태그의 콘텐츠 표시 지정
playsinline |
readonly    | 요소 편집을 불가능하게 해 읽기만 가능  
required    | 필드가 채워졌는지 확인 (필드에 따라 특정 값만 허용)
reversed    | ol 태그의 리스트를 내림차순으로 지정
selected    |
truespeed   |


```html
<tag disabled></tag>
<!--
: output 태그에는 지정 불가
: disabled 속성을 지정한 경우 유효성 검사를 하지 않음
: 입력 양식을 서버로 전송시 비활성화된 요소의 데이터는 전송하지 않음
-->


<tag multiple></tag>
<!-- select 태그와 input의 email, file 타입에 적용 가능 -->


<style>
:read-only {}
</style>

<tag readonly></tag>
<!--
: readonly 속성을 지정한 경우 유효성 검사를 하지 않음
: disabled 속성과 달리 요소의 데이터를 서버로 전송함
-->


<style>
:required {}
:valid {}
:invalid {}
</style>

<tag required aria-required="true"></tag>
<!-- input의 hidden, button, range, color 타입일 경우 적용 불가 -->
```



[top](#)
