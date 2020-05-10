# CSS Backgrounds & Borders
https://www.w3.org/TR/css-backgrounds/


- [background](#background)
- [border](#border)


속성 | 설명
---|---
box-shadow  | 상자에 그림자 효과 지정  



## background  
: 박스의 색이나 하나 이상의 이미지 지정   


속성 | 설명
---|---
background-color      | 배경 색 지정
background-image      | 배경 이미지 지정
background-repeat     | 배경 이미지의 반복 여부 지정
background-attachment | 배경 이미지의 스크롤 여부 지정
background-position   | 배경 이미지의 위치 지정
background-clip       | 배경 이미지를 테두리나 여백까지 채우기 위해 지정
background-origin     | 배경 이미지를 박스에 채우기 위한 위치 지정
background-size       | 배경 이미지 크기 지정


```css
* {background:color url() top left repeat border-box;}


* {background-color:transparent | color;}


* {background-image:url('');}


* {background-repeat:repeat | repeat-x | repeat-y | space | round | no-repeat;}
/*
- repeat
: 이미지를 반복하여 박스 영역 전체를 채우며 이미지가 넘칠 경우 짤림  

- space
: 이미지가 넘치지 않게 박스 영역 전체를 채움  
: 박스 영역 가장 자리부터 이미지를 채워 넣어 여백이 생길 수 있음
: 박스 영역보다 이미지가 크기가 큰 경우 이미지 짤림    

- round
: 박스에 여백을 남기지 않게 박스 영역을 채움
: 박스 크기가 달라지는 경우 이미지를 늘려 영역을 채움
*/


* {background-attachment:scroll | fixed | local;}
/*
- scroll : 박스 영역에서 배경 이미지 고정
- fixed : 뷰포트에서 배경 이미지 고정
- local : 박스 영역과 함께 배경 이미지 스크롤
*/


* {background-position:left | center | right | top | bottom;}
* {background-position:length | percentage;}

* {background-position:left top;}
/* 수치가 없으면 기본 값은 0 */

* {background-position:10px 10px;}
/* 두 개의 값을 지정할 경우 처음은 가로 위치 나중은 세로 위치 */


* {background-clip:border-box | padding-box | content-box | text;}
/*
: 이미지가 없을 경우 투명으로 영역이 채워짐

- border-box : 테투리 영역까지 배경 이미지를 채움
- padding-box : 여백 영역까지 배경 이미지를 채움
- content-box : 컨텐츠 영역에 배경 이미지를 채움
- text : 컨텐츠 영역의 텍스트에 배경 이미지를 채움  
*/


* {background-origin: border-box | padding-box | content-box;}


* {background-size:length | percentage;}


/* 배경 이미지 중첩 사용 */
* {background-image:url(''), url(''), url('');}
* {background-repeat:no-repeat, no-repeat, no-repeat;}
* {background-position:top left, center bottom, 0% 100%;}
```



## border
: 박스의 경계선-테두리의 스타일과 색 등을 지정  

\+ 외곽선


속성 | 설명
---|---
border-*-color  | 테두리의 색 지정
border-*-style  | 테두리의 스타일지정
border-*-width  | 테두리의 두께 지정
border-*-radius | 테두리의 모서리를 둥근 모서리로 지정
border-image-source | 테두리에 사용할 이미지 지정
border-image-slice  | 
border-image-width  |
border-image-outset |
border-image-repeat |


```css
* {border:1px solid red;}

* {border-color:color;}


* {border-style:none | hidden | dotted | dashed | solid | double | groove | ridge | inset | outset;}


* {border-width:length | thin | medium | thick;}


* {border-radius:length | percentage;}


* {border-image:url('');}
/*
: 테두리의 두께와 스타일을 기반으로 이미지 표현
: 이미지를 9개 구역으로 나누고 이를 제어  
1 | 2 | 3
4 | 5 | 6
7 | 8 | 9  
*/
```


**border style**    
![border style example](https://www.w3.org/TR/css-backgrounds/images/borderstyles.png)



[top](#)
