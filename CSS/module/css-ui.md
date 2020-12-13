# CSS UI

https://www.w3.org/TR/css-ui/


속성 | 설명
---|---
outline       | outline-* 속성 축약
outline-width | 외곽선 너비 지정
outline-style | 외곽선 스타일 지정
outline-color | 외곽선 색 지정
outline-offset| 외곽선과 보더의 간격 지정  
resize        | 요소의 크기 조정 여부 지정  
cursor        | 커서 타입 지정
caret         | caret-* 속성 축약
caret-color   | 텍스트 삽입 캐럿 색 지정
caret-shape   | 텍스트 삽입 캐럿 모양 지정
nav-*         | 방향키를 나타내는 키보드 제어
appearance    | 위젯 스타일 제어를 위한 방법 지정  


```css
E {outline:outline-color outline-style outline-width;}


E {outline-offset:length;}


E {resize:none | both | horizontal | vertical;}


E {cursor:keyword | img;}
/*
- default
- pointer
- progress
- wait
- help
- context-menu
- ...
*/


E {caret:caret-color caret-shape;}


E {caret-color:auto | color;}


E {caret-shape:auto | bar | block | underscore;}


E {nav-up:auto | id | target-name;}
E {nav-right:auto | id | target-name;}
E {nav-down:auto | id | target-name;}
E {nav-left:auto | id | target-name;}


E {appearance:none | auto | button | textfield | menulist-button | <compat-auto>;}
/*
compat-auto
https://www.w3.org/TR/css-ui/#typedef-appearance-compat-auto
*/
```



[top](#)
