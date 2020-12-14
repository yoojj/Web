# CSS Position

https://www.w3.org/TR/css-position/


속성 | 설명
---|---
position    | 박스의 위치를 결정하는 방법 지정  
top, bottom | 박스의 위치 지정
left, right | 박스의 위치 지정
inset       | inset-* 속성 축약
inset-block | inset-block-* 속성 축약
inset-block-start  |
inset-block-end    |
inset-inline       | inset-inline-* 속성 축약
inset-inline-start |
inset-inline-end   |


```css
E {position:static | relative | absolute | sticky | fixed;}
/*
static
: not a positioned box
: 컨텍스트에 따라 배치


relative
: 상대 위치 지정
: 현재 박스 위치에서 top~right 속성을 통해 박스 배치
: top~right 속성을 지정하지 않으면 static과 동일
: 상위 요소에 overflow 속성이 지정된 경우를 제외하면 다른 박스에 영향을 미치지 않음

E {position:relative;top:0;left:0;}

E {overflow:auto;}
E > F {position:relative;top:10%;left:10%;}


absolute
: 절대 위치 지정
: 부모 박스를 기준으로 top~right 속성을 통해 박스 배치  
: 부모 박스의 position 값이 static이 아니며 위치 값을 갖고 있어야 함  
: 부모 박스가 없을 경우 뷰포트의 0,0 좌표를 기준으로 배치
: 컨텍스트에서 벗어나므로 다른 박스의 크기나 위치에 영향을 미치지 않음  

E {position:relative;}
E > F {position:absolute;top:0;left:0;}


sticky
: 고정 위치 지정
: relative + fixed


fixed
: 고정 위치 지정
: 뷰포트의 0,0 좌표를 기준으로 top~right 속성을 통해 박스 배치  
: 컨텍스트에서 벗어나므로 다른 박스의 크기나 위치에 영향을 미치지 않음
: 스크롤에서 제외됨
*/


E {top:auto | length | percentage;bottom:0;left:0;right:0;}
/*
: top과 bottom 속성이 동시에 지정되면 top 속성이 우선 순위를 갖음
: left과 right 속성이 동시에 지정되면 dir 속성에 따라 우선 순위를 갖음
*/
```



[top](#)
