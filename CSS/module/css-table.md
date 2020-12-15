# CSS Table

https://www.w3.org/TR/css-tables/


속성 | 설명
---|---
table-layout    | 테이블 레이아웃 알고리즘 사용 여부 지정
border-collapse | 셀의 보더 표현 방법 지정
border-spacing  | 테이블 보더와 셀 보더 사이에 간격 지정
caption-side    | 캡션 위치 지정
empty-cells     | 빈 셀의 보더 표현 방법 지정


```css
E {table-layout:auto | fixed;}
/*
- auto : 콘텐츠가 셀의 크기를 벗어날 경우 셀 비율을 조절함
- fixed : (콘텐츠가 셀의 크기를 벗어나도) 셀 크기를 고정함
*/


E {border-collapse:separate | collapse;}
/*
: 테이블에도 보더가 존재하고 셀에도 보더가 존재

- separate : 셀의 보더를 표현  
- collapse : 테이블과 셀 사이에 인접한 보더를 합침  
*/


E {border-spacing:length;}
/*
: border-collapse:separate 경우 지정된 기본 값이 있음
: border-collapse:collapse 경우 적용되지 않음

E {border-collapse:separate;border-spacing:0;}
*/


E {caption-side:top | bottom;}


E {empty-cells:show | hide;}
/* border-collapse:collapse 경우 적용되지 않음 */
```



[top](#)
