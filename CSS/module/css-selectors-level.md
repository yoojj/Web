# CSS Selectors   

**레벨별 분류**
- [level 1](#level-1)
- [level 2](#level-2)
- [level 3](#level-3)
- [level 4](#level-4)



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



## level 2
패턴 | 명칭 | 설명
---|---|---
\*              | 전체 선택자 | 모든 요소 선택
E[ ]            | 속성 선택자 | 해당 속성을 가진 요소들 선택
E[a = b]        | 속성 선택자 | 해당 속성 값이 정확하게 일치하는 요소들 선택  
E[a ~= b]       | 속성 선택자 | 해당 속성 값이 포함되는 요소들 선택  
E[a &#166;= b]  | 속성 선택자 | 해당 속성 값과 일치하거나 속성 값으로 시작되는 요소들 선택  
E > F           | 자식 결합자 | E 요소의 바로 아래 존재하는 F 요소 선택
E + F           | 인접 형제 결합자 | E 요소를 따르는 F 요소가 존재하면 모두 선택


**linguistic pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:lang()        | 언어 의사 클래스 | 해당 속성 값으로 지정된 요소들 선택  


**user-action pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:hover         | pointer hover 의사 클래스 | 마우스 커서가 요소를 가르켜 활성화되는 요소 선택  
E:focus         | input focus 의사 클래스 | 키보드나 마우스에 의해 입력 요소에 입력을 받는 요소 선택    

\+ focusable area   
https://html.spec.whatwg.org/multipage/interaction.html#focusable-area


**tree-structural pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:first-child   | child-indexed 의사 클래스 | 해당 요소의 자식 중 첫번째 요소 선택


## level 3

패턴 | 명칭 | 설명
---|---|---
E[a ^= b]       | substring matching 속성 선택자 | 해당 속성 값으로 시작하는 E 요소 선택
E[a $= b]       | substring matching 속성 선택자 | 해당 속성 값으로 끝나는 E 요소 선택
E[a *= b]       | substring matching 속성 선택자 | 해당 속성 값이 포함되는 E 요소 선택
E ~ F           | 인접 형제 결합자 | E 요소 하위에 있는 모든 F 요소들 선택  
E:not()         | negation, matches-none 부정 의사 클래스 | 해당 요소를 제외한 요소 선택  


**location pseudo-classes**  

패턴 | 명칭 | 설명
---|---|---
E:target        | target 의사 클래스 |


**input pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:enabled       | 의사 클래스 | 활성화된 요소 선택
E:disabled      | 의사 클래스 | 비활성화된 요소 선택
E:read-write    | mutability 의사 클래스 | 사용자가 변경할 수 있는 입력 양식 요소 선택  
E:read-only     | mutability 의사 클래스 | 사용자가 변경할 수 없는 입력 양식 요소 선택  
E:placeholder-shown   | placeholder shown 의사 클래스 | placeholder 속성이 있는 입력 양식 요소 선택  
E:default       | default-option 의사 클래스 | 기본 범주에 있는 입력 양식 요소 선택   
E:checked       | selected-option 의사 클래스 | checked 된 입력 양식 요소 선택   
E:valid         | validity 의사 클래스 | 데이터 제약 조건에 만족한 입력 양식 요소 선택
E:invalid       | validity 의사 클래스 | 데이터 제약 조건에 실패한 입력 양식 요소 선택  
E:in-range      | range 의사 클래스 | 지정된 범위 내에 있는 입력 양식 요소 선택
E:out-of-range  | range 의사 클래스 | 지정된 범위에서 벗어난 입력 양식 요소 선택
E:required      | optionality 의사 클래스 | required 입력 양식 요소 선택
E:optional      | optionality 의사 클래스 | required가 아닌 입력 양식 요소 선택   

```html
<!-- :default -->
<style>
:default {width:50px;height:50px;}
/*
범주
input - checked
option - selected

button
input - button type
*/
</style>

<input type="checkbox" checked>
<input type="checkbox">
<input type="checkbox">


<!-- :vaild -->
<style>
:valid {background:green;}
:invalid {background:red;}
/* 제약 조건이 없는 요소는 valid가 적용 */
</style>

<input type="email">
```


**tree-structural pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:root                | root 의사 클래스 | 문서의 루트 요소 선택  
E:empty               | empty 의사 클래스 |
E:nth-child(n)        | child-indexed 의사 클래스 | 해당 요소의 자식 중 n번째 요소 선택
E:nth-last-child(n)   | child-indexed 의사 클래스 | 해당 요소의 자식 중 끝에서 시작한 n 번째 요소 선택  
E:nth-of-type(n)      | child-indexed 의사 클래스 |
E:nth-last-of-type(n) | child-indexed 의사 클래스 |
E:last-child          | child-indexed 의사 클래스 | 해당 요소의 자식 중 마지막 요소 선택
E:only-child          | child-indexed 의사 클래스 | 해당 요소의 유일한 자식 요소 선택  
E:first-of-type       | child-indexed 의사 클래스 | 해당 타입의 첫번째 자식 요소 선택
E:last-of-type        | child-indexed 의사 클래스 | 해당 타입의 마지막 자식 요소 선택  
E:only-of-type        | child-indexed 의사 클래스 | 해당 타입의 유일한 형제 요소 선택  



## level 4

패턴 | 명칭 | 설명
---|---|---
E:is(s)         | matches-any, 일치 의사 클래스 | 선택자 목록과 일치하는 요소 선택     
E:not(s)        | negation, matches-none 부정 의사 클래스 | +3 선택자 목록 추가  
E:where(s)      | specificity-adjustment |
E:has(s)        | relational, 관계형 의사 클래스 | 해당 선택자를 포함한 요소만 선택  
E[a = b i]      | case-sensitivity 속성 선택자 | 속성 값의 대소문자 구분을 하지 않음
E[a = b s]      | case-sensitivity 속성 선택자 | 속성 값 대소문자를 구분함  

```css
:is(html) {}
:is(html, body) {}
:is(select, article) h1 {}
:is(*:hover) {}
/*
브라우저에서 초안 단계에 사용했던 :matches()나 :any() 선택자로 지원하는 경우가 있으므로    
:is() 선택자 사용시 아래와 같은 접두사 전부 사용

:-moz-any()
:-webkit-any()
:matches()
*/
```


**linguistic pseudo-classes**

패턴 | 명칭 | 설명
---|---|---
E:dir()         | direction 의사 클래스 | 텍스트의 방향이 일치하는 요소 선택  
E:lang()        | language 의사 클래스 | +2 와일드 카드와 콤마 연산자 추가

```css
:lang(en-*) {}
```


**location pseudo-classes**  

패턴 | 명칭 | 설명
---|---|---
E:any-link()    | 하이퍼링크 의사 클래스 |
E:local-link    | 로컬 링크 의사 클래스 | 해당 요소의 url과 문서의 url이 일치하는 경우 선택  
E:target-within | target container 의사 클래스 |
E:scope         | reference element 의사 클래스 |


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
E:nth-child(n)        | child-indexed 의사 클래스 | +3
E:nth-last-child(n)   | child-indexed 의사 클래스 | +3


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
E:playing       | |
E:paused        | |



[top](#)
