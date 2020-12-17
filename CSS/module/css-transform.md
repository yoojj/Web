# CSS Transform

https://www.w3.org/TR/css-transforms/  
https://drafts.csswg.org/css-transforms/  


속성 | 설명
---|---
transform        | 요소의 좌표 공간을 변경하는 함수 지정  
transform-origin | 요소 기준 위치 지정    
transform-box    |


```css
E {transform:none transform-function;}
/*
: transform 속성을 적용한 요소는 새로운 스택 컨텍스트를 생성


이동 변환 함수
- translate(x,y)
- translate3d(x,y,z)
- translateX(x)
- translateY(y)
- translateZ(z)


회전 변환 함수
: 요소의 중심을 기점으로 요소를 회전
: grad, radian, turn 단위 사용   

- rotate(angle)
- rotate3d(x,y,z,angle)
- rotateX(x)
- rotateY(y)
- rotateZ(z)


크기 변환 함수
: 요소의 중심을 기점으로 요소를 축소하거나 확대  

- scale(x,y)
- scale3d(x,y,z)
- scaleX(x)
- scaleZ(y)
- scaleY(z)


비틀기 변환 함수
- skew(x,y)
- skewX(x)
- skewY(y)


원근감 변환 함수
perspective(d)


변환 행렬 함수
matrix(a, b, c, d, tx, ty)
matrix3d(a, b, 0, 0, c, d, 0, 0, 0, 0, 1, 0, tx, ty, 0, 1)


E {transform:translate(0px) rotate(0deg) scale(0,0);}
*/


E {transform-origin:left | right | top | center | bottom | length;}
/*
: rotate나 scale같은 요소 변환 함수는 요소의 중심을 기준으로 동작하는데
  이 위치를 변경하기 위한 속성  
*/


E {transform-box:content-box | border-box | fill-box | stroke-box | view-box;}
```



[top](#)
