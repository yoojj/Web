# CSS Selectors   



## level 4
패턴 | 명칭 | 설명
---|---|---
E:is(s)         | matches-any, 일치 의사 클래스 | 선택자 목록과 일치하는 요소 선택     
E:not(s)        | negation, matches-none 부정 의사 클래스 | 선택자 목록을 제외한 요소 선택
E:where(s)      | specificity-adjustment |
E:has(s)        | relational, 관계형 의사 클래스 |
E[속성='값' i]   | attribute case-sensitivity |
E[속성='값' s]   | attribute case-sensitivity |


**linguistic**

패턴 | 명칭 | 설명
---|---|---
E:dir()         | direction, 방향 의사 클래스 | 텍스트의 방향이 일치하는 요소 선택  
E:lang()        | language, 언어 의사 클래스 | 와일드 카드와 콤마 연산자 추가


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
