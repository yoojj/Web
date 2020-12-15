# CSS Box Sizing

https://www.w3.org/TR/css-sizing/


**box model**    
![css box model](https://www.w3.org/TR/css-box/images/box.png)


속성 | 설명
---|---
width, height | 상자의 너비와 높이 지정  
min-width, min-height | 상자의 최소 너비와 최소 높이 지정
max-width, max-height | 상자의 최대 너비와 최대 높이 지정
box-sizing    | 박스 크기를 결정하는 방법 지정
column-width  |


```css
E {width:auto | length-percentage | min-content | max-content | fit-content;}
E {min-width:auto | length-percentage | min-content | max-content | fit-content;}
E {max-width:none | length-percentage | min-content | max-content | fit-content;}
/*
- auto : 요소의 display에 따라 블록 박스와 인라인 박스 크기 지정
*/


E {box-sizing:content-box | border-box;}
/*
content-box
: width와 hegiht 속성으로 콘텐츠 박스 크기 지정
: padding 속성은 패딩 박스 크기를 border 속성은 보더 박스 크기를 지정
: width와 hegiht 속성 값과 추가되는 padding과 border 속성 값을 합해 박스를 그림


border-box
: width와 hegiht 속성으로 보더 박스 크기 지정
: width와 hegiht 속성 값으로 박스가 그려짐
*/


E {column-width:min-content | max-content | fit-content;}
```



[top](#)
