# CSS Pseudo Elements

https://www.w3.org/TR/css-pseudo/


가상 엘리먼트 | 설명
---|---
::first-line     | 요소의 첫 번째 줄 텍스트 선택  
::first-letter   | 요소의 첫 번째 줄 첫 번째 단어의 첫 글자 선택
::selection      | 드래그나 클릭된 강조된 텍스트 선택
::inactive-selection |
::spelling-error |
::grammar-error  |
::before         | 요소 앞에 가상 콘텐츠 삽입
::after          | 요소 뒤에 가상 콘텐츠 삽입
::marker         | 목록 요소의 마커 선택  
::placeholder    | 양식 요소의 placeholder 속성 값 선택



```css
E::first-line {}
/*
: 폰트, 텍스트, 배경관련 스타일 지정 가능
: 선택되는 텍스트의 양은 뷰포트 크기나 박스 크기 등 주변 요소에 따라 달라짐

body::first-line {적용됨}
span::first-line {적용되지 않음}

span {display:block;}
span::first-line {적용됨}

<body>
    <span>text</span>
</body>
*/


E::first-letter {}
/*
p::first-letter {적용되지 않음}

<p>
    <br>text
</p>
*/


E::selection {}
/* 레이아웃에 영향을 주지 않는 스타일만 적용 가능 */


E::before {}
E::after {}
/*
div {display:none;}
div::after {적용되지 않음}

<div></div>
*/


E::marker {}
/*
p {display:list-item;list-style-position:inside;}
p::marker {적용됨}

<div>
    <p>1
    <p>2
    <p>3
</div>
*/


E::placeholder {}
/*
::placeholder vs :placeholder-shown
:placeholder-shown는 placeholder 속성의 값에 대한 설정 불가

::placeholder {color:red;적용됨}
:placeholder-shown {color:red;적용되지 않음}
*/
```



[top](#)
