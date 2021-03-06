# CSS Selectors   

https://www.w3.org/TR/selectors/     
https://drafts.csswg.org/selectors/


**종류**   
1. [simple selector](#1-simple-selector)
2. [compound selector](#2-compound-selector)
3. [complex selector](#3-complex-selector)
4. [selector list](#4-selector-list)


**CSS Selector Priority-Specificity**   
: 선택자가 중첩될 경우 적용되는 선택자 우선 순위 규칙  



## 1. simple selector

종류 | 설명
---|---
type selector      | 타입 선택자
universal selector | 전체 선택자
attribute selector | 속성 선택자
class selector     | 클래스 선택자
id selector        | 아이디 선택자
pseudo-class selector  | 의사 선택자



### pseudo class selector   
: css3 부터 가상 클래스와 가상 엘리먼트 구분   

의사 선택자 | 설명
---|---
pseudo-classes           | ex. :hover, :focus, :active
functional-pseudo-class  | ex. :is(), :not()
pseudo-elements          | ex. ::before, ::after


**pseudo-classes 분류**  
- linguistic pseudo-classes
- location pseudo-classes
- user-action pseudo-classes
- input pseudo-classes
- tree-structural pseudo-classes
- grid-structural pseudo-classes
- time-dimensional pseudo-classes
- resource state pseudo-classes


**pseudo-elements**  
: 존재하지 않는 요소를 가상으로 생성해 사용  
: 구분하기 위해 더블 콜론을 사용하나 브라우저에서 싱글 콜론도 지원   



## 2. compound selector
: combinator로 분리되지 않은 두 개 이상의 simple selector    

```css
*.class {}
```



## 3. complex selector
: combinator가 사용된 simple selector list  


**combinator**

결합자 | 설명 | 기호
---|---|---
descendant combinator          | 자손 결합자 | 공백
child combinator               | 자식 결합자 | >
next-sibling combinator        | 인접 형제 결합자 | +
subsequent-sibling combinator  | 인접 형제 결합자 | ~
column combinator              | 컬럼 결합자 | &#166;&#166;



## 4. selector list
: 콤마로 구분 된 선택자 목록   

```css
E,
E F,
E > F {}

h1,
h2..ex,
h3 {color:red;}
/* 유효하지 않은 선택자가 있을 경우 전부 무시됨 */
```



[top](#)
