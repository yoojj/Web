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
E:link          | link history 의사 클래스
E:visited       | link history 의사 클래스
E:active        | 동적 의사 선택자
E::first-line   | 가상 요소 선택자
E::first-letter | 가상 요소 선택자
E F             | 자손 결합자



## level 2
패턴 | 명칭 | 설명
---|---|---
\*              | 전체 선택자 | 모든 요소 선택
E[]             | 속성 선택자 | 해당 속성을 가진 요소들 선택
E[a = b]        | 속성 선택자 | 해당 속성 값이 정확하게 일치하는 요소들 선택  
E[a ~= b]       | 속성 선택자 | 해당 속성 값이 포함되는 요소들 선택  
E[a &#166;= b]  | 속성 선택자 | 해당 속성 값과 일치하거나 속성 값으로 시작되는 요소들 선택  
E:lang()        | 언어 의사 클래스 | 해당 속성 값으로 지정된 요소들 선택  
E:hover         | 의사 클래스 |
E:focus         | 의사 클래스 |
E:first-child   | 의사 클래스 | 해당 요소의 첫번째 자식 요소 선택  
E::before       | 의사 클래스 | 해당 요소의 첫 자식이 되는 가상 요소 생성  
E::after        | 의사 클래스 |
E > F           | 자식 결합자 | E 요소의 바로 아래 존재하는 F 요소 선택
E + F           | 인접 형제 결합자 | E 요소를 따르는 F 요소가 존재하면 모두 선택



## level 3

패턴 | 명칭 | 설명
---|---|---
E[a ^= b]       | substring matching 속성 선택자 | 해당 속성 값으로 시작하는 E 요소 선택
E[a $= b]       | substring matching 속성 선택자 | 해당 속성 값으로 끝나는 E 요소 선택
E[a *= b]       | substring matching 속성 선택자 | 해당 속성 값이 포함되는 E 요소 선택
E ~ F           | 인접 형제 결합자 | E 요소 하위에 있는 모든 F 요소들 선택  
E:not()         | negation, matches-none 부정 의사 클래스 | 해당 요소를 제외한 요소 선택  


**location**  

패턴 | 명칭 | 설명
---|---|---
E:target        | target 의사 클래스 |



**input**

패턴 | 명칭 | 설명
---|---|---
E:enabled       | 의사 클래스 |
E:disabled      | 의사 클래스 |
E:read-write    | 의사 클래스 |
E:read-only     | 의사 클래스 |
E:placeholder-shown   | placeholder shown 의사 클래스 |
E:default       | default-option 의사 클래스 |
E:checked       | 의사 클래스 |
E:valid         | 의사 클래스 |
E:invalid       | 의사 클래스 |
E:in-range      | 의사 클래스 |
E:out-of-range  | 의사 클래스 |
E:required      | 의사 클래스 |
E:optional      | 의사 클래스 |


**tree-structural**

패턴 | 명칭 | 설명
---|---|---
E:root                | root 의사 클래스 | 문서의 루트 요소 선택  
E:empty               | empty 의사 클래스 |
E:nth-child(n)        | 의사 클래스 | E 요소의 자식 중 n번째 요소 선택
E:nth-last-child(n)   | 의사 클래스 | E 요소의 자식 중 끝에서 시작한 n 번째 요소 선택  
E:nth-of-type(n)      | 의사 클래스 |
E:nth-last-of-type(n) | 의사 클래스 |
E:first-child         | 의사 클래스 | E 요소의 자식 중 첫번째 요소 선택
E:last-child          | 의사 클래스 | E 요소의 자식 중 마지막 요소 선택
E:only-child          | 의사 클래스 | E 요소의 유일한 자식 요소 선택  
E:first-of-type       | 의사 클래스 | 해당 타입의 첫번째 자식 요소 선택
E:last-of-type        | 의사 클래스 | 해당 타입의 마지막 자식 요소 선택  
E:only-of-type        | 의사 클래스 | 해당 타입의 유일한 형제 요소 선택  



## level 4

패턴 | 명칭 | 설명
---|---|---
E:is(s)         | matches-any, 일치 의사 클래스 | 선택자 목록과 일치하는 요소 선택     
E:not(s)        | negation, matches-none 부정 의사 클래스 | 선택자 목록을 제외한 요소 선택
E:where(s)      | specificity-adjustment |
E:has(s)        | relational, 관계형 의사 클래스 |
E[a = b i]      | case-sensitivity |
E[a = b s]      | case-sensitivity |


**linguistic**

패턴 | 명칭 | 설명
---|---|---
E:dir()         | direction 의사 클래스 | 텍스트의 방향이 일치하는 요소 선택  
E:lang()        | language 의사 클래스 | 와일드 카드와 콤마 연산자 추가


**location**  

패턴 | 명칭 | 설명
---|---|---
E:any-link()    | 하이퍼링크 의사 클래스 | :link + :visited
E:local-link    | 로컬 링크 의사 클래스 | 요소의 url과 문서의 url이 일치하는 경우 선택  
E:target-within | target container 의사 클래스 |
E:scope         | reference element 의사 클래스 |


**user-action**

패턴 | 명칭 | 설명
---|---|---
E:focus-within  | focus container 의사 클래스 |  
E:focus-visible | focus indicated 의사 클래스 |


**input**

패턴 | 명칭 | 설명
---|---|---
E:indeterminate | indeterminate value 의사 클래스 |
E:blank         | empty value 의사 클래스 | 입력 요소가 비어있는 경우 선택  
E:user-invalid  | user interaction |


**tree-structural**

패턴 | 명칭 | 설명
---|---|---
E:nth-child(n [of S]?)      | |
E:nth-last-child(n [of S]?) | |


**grid-structural**     

패턴 | 명칭 | 설명
---|---|---
E:nth-col(An+B)        |  |
E:nth-last-col(An+B)   |  |
col &#166;&#166; cell  | column combination, 열 조합 선택자 |


**time-dimensional**

패턴 | 명칭 | 설명
---|---|---
E:current       | current element 의사 클래스 |
E:current()     | current element 의사 클래스 |
E:past          | past element 의사 클래스 |  
E:future        | future element 의사 클래스 |


**resource state**

패턴 | 명칭 | 설명
---|---|---
E:playing       | |
E:paused        | |


```css
:is(html) {}
:is(html, body) {}
:is(select, article) h1 {}
:is(*:hover) {}
/*
브라우저에서 초안 단계였던 :matches()나 :any() 선택자로 지원하는 경우가 있으므로    
:is() 선택자 사용시 아래와 같은 접두사 전부 사용해야 함

:-moz-any()
:-webkit-any()
:matches()
*/


:lang(en-*) {}


form:focus-within {background:gray;}
/*
<form>
    input에 포커스 할 경우 form 배경색 변경
    <input type="text">
</form>
*/
```



[top](#)
