# CSS Background & Border

https://www.w3.org/TR/css-backgrounds/


**background**   
: 박스는 투명하거나 색으로 채워지거나 하나 이상의 이미지로 채워짐     
: background 속성을 통해 박스를 채울 색상이나 이미지 지정   


**border**   
: 박스의 경계선-테두리의 스타일과 색 등 지정   


속성 | 설명
---|---
background            | background-* 속성 축약
background-color      | 배경 색 지정
background-image      | 배경 이미지 지정
background-repeat     | 배경 이미지 반복 방법 지정
background-attachment | 배경 이미지 스크롤 방법 지정
background-position   | 배경 이미지 위치 지정
background-clip       | 배경 이미지를 테두리나 여백까지 채우기 위한 방법 지정
background-origin     | 배경 이미지를 박스에 채우기 위한 위치 지정
background-size       | 배경 이미지 크기 지정
border          | border의 color, style, width 축약
border-*-color  | 보더 색 지정
border-*-style  | 보더 스타일 지정
border-*-width  | 보더 두께 지정
border-radius   | border-radius 축약
border-*-radius | 보더의 모서리를 둥근 모서리로 지정
border-image        | border-image-* 축약
border-image-source | 보더에 적용할 이미지 지정
border-image-slice  | 보더 이미지를 9개 영역으로 잘라 이를 표현하는 방법 지정
border-image-width  | 보더 이미지 너비 지정   
border-image-outset | 보더와 보더 이미지의 거리 지정  
border-image-repeat | 보더 이미지의 크기 조정 방법 지정
box-shadow	        | 박스에 그림자 효과 지정


```css
E {background-color:transparent | color;}


E {background-image:img | none;}
/* 색과 이미지 둘 다 적용하면 색 위에 이미지가 그려짐 */


E {background-repeat:repeat | repeat-x | repeat-y | space | round | no-repeat;}
/*
- repeat
: 이미지를 반복해서 박스 영역 전체를 채우며 이미지가 넘칠 경우 짤림  

- space
: 이미지가 넘치지 않게 박스 영역 전체를 채움  
: 박스 영역 가장 자리부터 이미지를 채워 넣어 여백이 생길 수 있음
: 박스 영역보다 이미지가 크기가 큰 경우 이미지 짤림    

- round
: 박스에 여백을 남기지 않게 박스 영역을 채움
: 박스 크기가 달라지는 경우 이미지를 늘려 영역을 채움
*/


E {background-attachment:scroll | fixed | local;}
/*
- scroll : 박스 영역에서 배경 이미지 고정
- fixed : 뷰포트에서 배경 이미지 고정
- local : 박스 영역과 함께 배경 이미지 스크롤
*/


E {background-position:left | center | right | top | bottom | length;}


E {background-clip:border-box | padding-box | content-box;}
/*
: 이미지가 없을 경우 투명으로 영역이 채워짐

- border-box : 테투리 영역까지 배경 이미지를 채움
- padding-box : 여백 영역까지 배경 이미지를 채움
- content-box : 컨텐츠 영역에 배경 이미지를 채움
*/


E {background-origin:border-box | padding-box | content-box;}


E {background-size:auto | cover | contain | length;}


E {border:border-with border-style border-color;}


E {border-color:color;}


E {border-style:none | hidden | dotted | dashed | solid | double | groove | ridge | inset | outset;}


E {border-width:thin | medium | thick | length;}


E {border-radius:length | percentage;}


E {border-image-source:none | img;}


E {border-image-slice:number | fill;}

```


**border style**    
![border style example](https://www.w3.org/TR/css-backgrounds/images/borderstyles.png)



[top](#)
