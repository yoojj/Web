# CSS Multi-column Layout

https://www.w3.org/TR/css-multicol/


속성 | 설명
---|---
columns           | column-width, column-count 속성 축약
column-width      | 컬럼 너비 지정
column-count      | 컬럼 단 수 지정
column-gap        | 컬럼 사이 간격 지정
column-rule       | column-rule-* 속성 축약  
column-rule-color | 컬럼 사이 라인의 색 지정
column-rule-style | 컬럼 사이 라인의 스타일 지정
column-rule-width | 컬럼 사이 라인의 너비 지정
column-span       | 컬럼이 모든 단을 차지하는지 여부 지정   
column-fill       | 콘텐츠가 단을 채우는 방법 지정  


**multi column container**  
: column-width이나 column-count 속성이 적용된 블록 박스        
: 멀티 컬럼 모델에서 부모가 되는 박스   
: 멀티 컬럼 컨테이너는 분열(fragmentation) 컨텍스트를 생성   


**column boxes**   
: 멀티 컬럼 모델에서 자식이 되는 박스     


```css
E {column-count:column-width column-count;}


E {column-width:auto | length;}
/*
auto
: column-gap 속성 값에 맞춰 지정됨

length
: (컨테이너 공간 - column-gap)/column-width의 결과로 지정된 단 수에 맞춰
  지정한 너비 값이 조절됨  
: 컨테이너 공간보다 큰 너비를 지정할 경우 하나의 단을 생성   
*/


E {column-count:auto | integer;}
/*
auto
: (컨테이너 공간 - column-gap)/column-width의 결과를 반내림한 값을 단 수 지정  
*/


E {column-gap:normal | length;}


E {column-rule:column-rule-width column-rule-style column-rule-color;}


E {column-rule-color:color;}


E {column-rule-style:<border-style>;}
/*
border-style
https://www.w3.org/TR/css-backgrounds/#typedef-line-style
*/


E {column-rule-width:thin | medium | thick | length;}


/*
컬럼 나누기
https://www.w3.org/TR/css-break/#breaking-controls

- break-after
- break-before
- break-inside


E {break-after:auto | avoid | avoid-page | page | left | right | recto | verso | avoid-column | column | avoid-region | region;}

E {break-before:auto | avoid | avoid-page | page | left | right | recto | verso | avoid-column | column | avoid-region | region;}

E {break-inside:auto | avoid | avoid-page | avoid-column | avoid-region;}


E {column-count:3;}
E > F {break-after:avoid;}
*/


E > F {column-span:none | all;}
/*
all
: 컬럼이 적용된 column-count 만큼의 단 수를 차지함
: 멀티 컬럼 컨테이너의 흐름에서 벗어남
*/


E {column-fill:auto | balance | balance-all;}
```



[top](#)
