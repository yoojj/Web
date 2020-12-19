# CSS Multi-column Layout

https://www.w3.org/TR/css-multicol/


속성 | 설명
---|---
columns           | column-width, column-count 속성 축약
column-width      | 컬럼 너비 지정
column-count      | 컬럼 개수 지정
column-gap        | 컬럼 사이 간격 지정
column-rule       | column-rule-* 속성 축약  
column-rule-color | 컬럼 사이 라인의 색 지정
column-rule-style | 컬럼 사이 라인의 스타일 지정
column-rule-width | 컬럼 사이 라인의 너비 지정
column-span       |
column-fill       |


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
auto : column-gap 속성 값에 맞춰 지정
*/


E {column-count:auto | integer;}
/*
auto : column-width 속성 값에 맞춰 지정
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


E > F {column-span:none | all;}


E > F {column-fill:auto | balance | balance-all;}
```


[top](#)
