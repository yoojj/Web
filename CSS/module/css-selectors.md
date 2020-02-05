# CSS Selectors   

https://www.w3.org/TR/selectors/   


**선택자 종류**   
- [simple selector](#simple-selector)
- [compound selector](#compound-selector)
- [complex selector](#complex-selector)


**CSS Selector Priority-Specificity**   
: 선택자 우선 순위 적용을 위해 사용되는 규칙  



## simple selector

종류 | 설명
---|---
type selector      | 타입 선택자
universal selector | 전체 선택자
attribute selector | 속성 선택자
class selector     | 클래스 선택자
id selector        | 아이디 선택다
pseudo-class selector  | 의사 선택자


### pseudo class selector   
: css3 부터 가상 클래스와 가상 엘리먼트 구분   

- [pseudo-classes](#pseudoclasses)
- [pseudo-elements](#pseudoelements)


#### pseudo-classes
: 선택한 요소에 클래스를 부여하지 않았어도 클래스를 부여한 것과 같은 효과

- :active
- :any
- :checked
- :default
- ...
- :visited

**functional-pseudo-class**  
- :dir()
- :lang()
- ...



#### pseudo-elements  
: 존재하지 않는 요소를 가상으로 생성하여 사용  

- ::after
- ::before
- ::first-letter
- ::first-line
- ::selection
- ::backdrop



## compound selector
: combinator로 분리되지 않은 simple selector  

```css
*.class {}
```



## complex selector
: combinator가 사용된 simple selector


### combinator

결합자 | 설명 | 기호
---|---|---
descendant combinator          | 자손 결합자 | 공백
child combinator               | 자식 결합자 | >
next-sibling combinator        | 인접 형제 결합자 | +
subsequent-sibling combinator  | 인접 형제 결합자 | ~



[top](#)
