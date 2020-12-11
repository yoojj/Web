# CSS Selectors   


- [level 1](#level-1)
- [level 2](#level-2)
- [level 3](#level-3)
- [level 4](#level-4)
- [pseudo-elements](#pseudo-elements)



## level 1
패턴 | 명칭
---|---
E               | 타입 선택자
.class          | 클래스 선택자
\#id            | 아이디 선택자
E F             | 자손 결합자


**user-action pseudo-classes**

패턴 | 명칭
---|---
E:link          | link history 의사 클래스
E:visited       | link history 의사 클래스
E:active        | activation 의사 클래스


**:visited**    
: 보안 문제로 일부 브라우저에서 기능이 제한됨    

https://developer.mozilla.org/en-US/docs/Web/CSS/Privacy_and_the_:visited_selector



## level 2
패턴 | 명칭 | 설명
---|---|---
\*              | 전체 선택자 | 모든 요소 선택
E[attr]         | 속성 선택자 | 해당 속성을 갖는 E 요소 선택
E[a = b]        | 속성 선택자 | 해당 속성의 값과 정확하게 일치하는 E 요소 선택  
E[a ~= b]       | 속성 선택자 | 해당 속성의 값이 포함되는 E 요소 선택  
E[a &#166;= b]  | 속성 선택자 | 해당 속성의 값과 일치하거나 속성의 값으로 시작되는 E 요소 선택  
E > F           | 자식 결합자 | E 요소의 바로 아래 존재하는 F 요소 선택
E + F           | 인접 형제 결합자 | E 요소를 따르는 F 요소가 존재하면 모두 선택

```css
:[title ~= 'text'] {}
:[lang |= 'ko'] {}
```


**linguistic pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:lang(attr)    | 언어 의사 클래스 | 해당 속성의 값으로 지정된 E 요소 선택  


**user-action pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:hover         | pointer hover 의사 클래스 | 마우스 커서가 요소를 가르켜 활성화되는 E 요소 선택  
E:focus         | input focus 의사 클래스 | 키보드나 마우스에 의해 입력 요소에 입력을 받는 E 요소 선택    


\+ focusable area   
https://html.spec.whatwg.org/multipage/interaction.html#focusable-area


**tree-structural pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:first-child   | child-indexed 의사 클래스 | E 요소의 자식 중 첫번째 요소 선택



## level 3

패턴 | 명칭 | 설명
---|---|---
E[a ^= b]       | substring matching 속성 선택자 | 해당 속성의 값으로 시작하는 E 요소 선택
E[a $= b]       | substring matching 속성 선택자 | 해당 속성의 값으로 끝나는 E 요소 선택
E[a *= b]       | substring matching 속성 선택자 | 해당 속성의 값이 포함되는 E 요소 선택
E ~ F           | 인접 형제 결합자 | E 요소 하위에 있는 모든 F 요소들 선택  
E:not(s)        | negation, matches-none 부정 의사 클래스 | 선택자를 제외한 E 요소 선택  


**location pseudo-classes**  

패턴 | 명칭 | 설명
---|---|---
E:target        | target 의사 클래스 | 활성화된 링크의 대상이되는 E 요소 선택  

```html
<!-- http://www.example.com/index.html#about -->
<div id="about"></div>
```


**input pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:enabled       | 의사 클래스 | 활성화된 양식 요소 선택
E:disabled      | 의사 클래스 | 비활성화된 양식 요소 선택
E:read-write    | mutability 의사 클래스 | 사용자가 변경할 수 있는 양식 요소 선택  
E:read-only     | mutability 의사 클래스 | 사용자가 변경할 수 없는 양식 요소 선택  
E:placeholder-shown   | placeholder shown 의사 클래스 | placeholder 속성이 있는 양식 요소 선택  
E:default       | default-option 의사 클래스 | 기본 범주에 있는 양식 요소 선택   
E:checked       | selected-option 의사 클래스 | 선택된 양식 요소 선택   
E:valid         | validity 의사 클래스 | 데이터 제약 조건에 만족한 양식 요소 선택
E:invalid       | validity 의사 클래스 | 데이터 제약 조건에 실패한 양식 요소 선택  
E:in-range      | range 의사 클래스 | 지정된 범위 내에 있는 양식 요소 선택
E:out-of-range  | range 의사 클래스 | 지정된 범위에서 벗어난 양식 요소 선택
E:required      | optionality 의사 클래스 | 필수 입력인 양식 요소 선택
E:optional      | optionality 의사 클래스 | 필수 입력이 아닌 양식 요소 선택   

```html
<!-- :read-only -->
<style>
:read-only {}
</style>

<input type="text" value="" readonly>


<!-- :default -->
<style>
:default {}
/*
input : checked
option : selected
button : button type
input  : button type
*/
</style>

<input type="checkbox" checked>
<input type="radio" checked>


<!-- :vaild -->
<style>
/* 제약 조건이 없는 요소는 valid로 적용됨 */
:valid {}
:invalid {}
</style>

<input type="email">


<!-- :in-range -->
<style>
:in-range {}
</style>

<input type="range" min="1" max="100">
<input type="number" min="1" max="100">
```


**tree-structural pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:root                | root 의사 클래스 | 웹 문서의 루트 요소 선택  
E:empty               | empty 의사 클래스 | 콘텐츠가 없는 E 요소 선택  
E:nth-child(n)        | child-indexed 의사 클래스 | E 요소의 자식 중 n번째 요소 선택
E:nth-last-child(n)   | child-indexed 의사 클래스 | E 요소의 자식 중 끝에서 시작한 n번째 요소 선택  
E:nth-of-type(n)      | child-indexed 의사 클래스 | 해당 타입 중 n번째 요소 선택
E:nth-last-of-type(n) | child-indexed 의사 클래스 | 해당 타입 중 끝에서 시작한 n번째 요소 선택
E:last-child          | child-indexed 의사 클래스 | E 요소의 자식 중 마지막 요소 선택
E:only-child          | child-indexed 의사 클래스 | E 요소의 유일한 자식 요소 선택  
E:first-of-type       | child-indexed 의사 클래스 | 해당 타입의 첫번째 자식 요소 선택
E:last-of-type        | child-indexed 의사 클래스 | 해당 타입의 마지막 자식 요소 선택  
E:only-of-type        | child-indexed 의사 클래스 | 해당 타입의 유일한 형제 요소 선택  

```css
/* 사용자 정의 속성을 위해 사용 */
:root {
    --red-color:red;
}

E {
    color:var(--red-color);
}


/* <div></div> */
:empty {}


/* 동일한 요소를 선택함 */
:nth-child(1) {}
:first-child {}

:nth-last-child(1) {}
:last-child {}
```



## level 4


패턴 | 명칭 | 설명
---|---|---
E:is(s)         | matches-any, 일치 의사 클래스 | 선택자 목록과 일치하는 E 요소 선택     
E:not(s)        | negation, matches-none 부정 의사 클래스 | (level 3) 선택자 목록  
E:where(s)      | specificity-adjustment 의사 클래스 | 선택자 목록과 일치하는 E 요소 선택  
E:has(s)        | relational, 관계형 의사 클래스 | 해당 선택자를 포함한 E 요소만 선택  
E[a = b i]      | case-sensitivity 속성 선택자 | 속성 값의 대소문자 구분을 하지 않음
E[a = b s]      | case-sensitivity 속성 선택자 | 속성 값 대소문자를 구분함  

```css
:is(html) {}
:is(html, body) {}
:is(section, article) h1 {}
:is(*:hover) {}
/*
브라우저에서 초안 단계에 사용했던 :matches()나 :any() 선택자로 지원하는 경우가 있으므로    
:is() 선택자 사용시 아래와 같은 접두사 전부 사용

:-moz-any()
:-webkit-any()
:matches()
*/



:where(section, article, aside):hover {}
input:where(:not(input[type='button'])) {}
```


**linguistic pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:dir()         | direction 의사 클래스 | 텍스트의 방향이 일치하는 요소 선택  
E:lang()        | 언어 의사 클래스 | (level 2) 와일드 카드와 콤마 연산자 추가

```css
:lang(en-*) {}
```


**location pseudo-classes**  

패턴 | 명칭 | 설명
---|---|---
E:any-link      | 하이퍼링크 의사 클래스 | 링크를 갖는 요소 선택
E:local-link    | 로컬 링크 의사 클래스 | 요소의 url과 웹 문서의 url이 일치하는 경우 선택  
E:target-within | target container 의사 클래스 |
E:scope         | reference element 의사 클래스 |

```css
:any-link {}
/* a, area, link의 href 속성이 있으면 모두 선택 */
```


**user-action pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:focus-within  | focus container 의사 클래스 |  
E:focus-visible | focus indicated 의사 클래스 |

```html
<style>
form:focus-within {background:gray;}
</style>

<form>
    <input type="text">
</form>
```


**input pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:indeterminate | indeterminate value 의사 클래스 |
E:blank         | empty value 의사 클래스 | 입력 요소가 비어있는 경우 선택  
E:user-invalid  | user interaction |


**tree-structural pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:nth-child(n)        | child-indexed 의사 클래스 | (level 3)
E:nth-last-child(n)   | child-indexed 의사 클래스 | (level 3)


**grid-structural pseudo-classes**     

패턴 | 명칭 | 설명
---|---|---
col &#166;&#166; cell  | column combination, 열 조합 선택자 |
E:nth-col(An+B)        | 의사 클래스 |
E:nth-last-col(An+B)   | 의사 클래스 |


**time-dimensional pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:current       | current element 의사 클래스 |
E:current()     | current element 의사 클래스 |
E:past          | past element 의사 클래스 |  
E:future        | future element 의사 클래스 |


**resource state pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:playing       | 리소스 상태 의사 클래스 | video 태그가 재생 상태인 경우 선택
E:paused        | 리소스 상태 의사 클래스 | video 태그가 일시 정지 상태인 경우 선택



## pseudo-elements

가상 엘리먼트 | 설명
---|---
E::after        | E 요소의 뒤에 가상 콘텐츠 삽입
E::backdrop     | E 요소의 뒤에 뷰포트 크기의 가상 배경을 삽입  
E::before       | E 요소의 앞에 가상 콘텐츠 삽입
E::cue          |
E::cue-region   |
E::first-letter |
E::first-line   |
E::file-selector-button |
E::grammar-error|
E::marker       |
E::part()       |
E::placeholder  | placeholder 속성에 스타일 적용  
E::selection    | 사용자에 의해 강조(드래그, 클릭)되는 텍스트에 텍스트 관련 스타일 적용
E::slotted()    |
E::spelling-error |

```css
::selection,
::-moz-selection {
    /* 일부 스타일만 사용 가능 */
    outline:none;
    text-decoration:none;
    text-shadow:none;
    color:#fff;
    background-color:#000;
}
```



[top](#)
